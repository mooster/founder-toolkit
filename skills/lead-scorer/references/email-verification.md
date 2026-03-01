# Email Deliverability Verification

Three-layer verification architecture for validating email addresses before outreach.

## Layer 1: Syntax Check (instant)

Validate email format with regex and flag suspicious patterns:
- Double dots (`..`)
- Dot-dash combinations (`.-`)
- Single character local part (`a@domain.com`)
- Known disposable email domains (mailinator, guerrillamail, etc.)

## Layer 2: MX Record Lookup (fast, bulk-safe)

Query DNS for the domain's mail exchange records.

**Classification:**
| MX Status | Meaning | Action |
|-----------|---------|--------|
| OK | Domain has mail servers | Proceed to Layer 3 |
| NXDOMAIN | Domain does not exist | Mark as bounce |
| NO_MX_HAS_A | Has A record but no MX | Likely bounce, flag |
| TIMEOUT | DNS query timed out | Retry once, then mark uncertain |
| NO_RECORDS | No DNS records at all | Mark as bounce |

**Implementation notes:**
- Use `dnspython` library for DNS queries
- 50 concurrent threads, 5-second timeout per query
- Run twice for better results (DNS cache warming on second pass)

## Layer 3: SMTP RCPT TO Verification (slow, precise)

Connect to the mail server and verify the specific mailbox exists.

**Process:**
1. Connect to MX server on port 25 (fallback to 587)
2. Send EHLO
3. Send MAIL FROM with a test address
4. Send RCPT TO with the target email
5. Check response code

**Response codes:**
| Code | Meaning | Classification |
|------|---------|---------------|
| 250 | Mailbox exists | DELIVERABLE |
| 550 | Mailbox does not exist | BOUNCE |
| 450/451/452 | Temporary failure | UNCERTAIN |
| 552 | Mailbox full | LIKELY_BOUNCE |

**Catch-all detection:**
- For each domain, test a fake address: `zzzfake9999nonexist@domain.com`
- If the server returns 250, it is a catch-all domain
- Mark all 250 results from catch-all domains as `LIKELY_DELIVERABLE_CATCHALL`

**Implementation notes:**
- 10 concurrent threads, 10-second timeout
- Group emails by domain to reuse TCP connections
- Gmail/Outlook are always catch-all — SMTP verification is ineffective for these

## Expected Results

Based on production test of 8,221 contacts:
- MX-only: 80.1% deliverable, 3.3% bounce, 16.5% uncertain
- MX + SMTP: 83.5% deliverable, 13.0% bounce, 3.5% uncertain
- SMTP resolved 691 of 1,353 uncertain addresses as bounce

## Script Generation

When the user needs to run verification at scale, offer to generate Python scripts:
- Layer 1+2: Single script with `dnspython`, 50-thread concurrent
- Layer 3: Separate script with `smtplib`, 10-thread concurrent
- Both output CSV with per-email results
