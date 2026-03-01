---
name: investor-update
description: This skill should be used when the user asks to "write an investor update", "investor letter", "monthly update to investors", "quarterly update", "投资人月报", "给投资人写 update", "board update", or wants to communicate company progress to investors or board members. Generates concise, professional updates following YC and a16z best practices.
---

# Investor Update Writer

Generate concise, professional investor updates that keep investors informed and engaged.

## Process

### Step 1: Gather Key Data

Collect the following inputs. Skip any the user does not have — calculate derivable values automatically (e.g., runway = cash / burn).

**Required inputs:**
- MRR or ARR (and previous period for comparison)
- Cash balance and monthly burn rate
- 2-3 highlights from this period
- 1-2 challenges or asks

**Optional inputs (auto-calculate when possible):**
- Customer count (new, churned, total)
- Key hires or team changes
- Product milestones
- Fundraising status

**Important:** Do not ask for values that can be derived. Given cash ($500K) and burn ($50K/mo), calculate runway as 10 months directly.

### Step 2: Generate the Update

Follow this structure. For detailed formatting guidance and examples, consult `references/update-format.md`.

```
Subject: [Company Name] — [Month Year] Investor Update

## TL;DR
[3 sentences max. Lead with most important news. Honest about tough months.]

## Key Metrics
[Table: Metric | This Month | Last Month | Change]

## Highlights
[2-3 concrete achievements with numbers]

## Challenges
[Honest assessment — not sugarcoated, not catastrophized]

## Asks
[Specific, actionable requests — "Intro to VP Eng at X" not "help with hiring"]

## What's Next
[2-3 priorities for next period]
```

### Step 3: Tone Verification

Before output, verify against these criteria:

- **Honest but not dramatic** — "Growth slowed to 5% as we focused on retention" not "We're struggling"
- **Specific not vague** — Numbers, names, dates. Not "things are going well"
- **Concise** — Entire update under 500 words. Investors read dozens of these
- **Actionable asks** — "Can you intro us to [specific person/company]?" not "We need help with sales"
- **No jargon dumping** — Write for a smart generalist, not a domain expert

### Language Handling

- Default to English
- When user inputs in Chinese, output in Chinese with the same structure
- Metric names remain in English even in Chinese updates (ARR, MRR, NRR are universal)

## Anti-Patterns

Avoid these common mistakes:

- Padding with fluff ("We're excited to share...")
- Hiding bad news — investors respect honesty and lose trust when surprised later
- Making it longer than necessary — a quiet month deserves a short update
- Including vanity metrics without context (page views without conversion)
- Asking for generic "advice" instead of specific intros or help

## Additional Resources

### Reference Files

- **`references/update-format.md`** — Detailed formatting guide with complete examples, subject line patterns, and metric presentation best practices.
