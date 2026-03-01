---
name: lead-scorer
description: Score and prioritize outreach leads using ICP-first methodology. Use when user mentions "lead scoring", "outreach", "qualify leads", "score companies", "prioritize prospects", "ICP matching", "评分", "打分", "outreach list", or wants to evaluate companies for sales/BD outreach.
---

# Outreach Lead Scorer

Score and prioritize companies for outreach using an ICP-first methodology. Based on a production system that scored 300+ companies.

## Process

### Step 1: Define ICP (Ideal Customer Profile)

Ask the user to define their ideal customer. If they're unsure, help them think through:

- **Industry**: What verticals? (e.g., fintech, SaaS, healthcare)
- **Size**: Employee count or revenue range?
- **Geography**: Target regions?
- **Key signals**: What makes a company especially good? (e.g., recent funding, specific tech stack, regulatory need)
- **Disqualifiers**: What makes a company a bad fit? (e.g., too small, wrong vertical, competitor)

Output the ICP as a structured scorecard before proceeding:

```
ICP Scorecard:
- Industry: [weight X/10]
- Size: [weight X/10]
- Geography: [weight X/10]
- Signal 1: [weight X/10]
- Signal 2: [weight X/10]
Disqualifiers: [list]
```

### Step 2: Input Company Data

Accept data from:
- **CSV/spreadsheet** — read and parse columns
- **Manual list** — user types or pastes company names
- **HubSpot** — if HubSpot MCP is available, pull from CRM

Minimum data needed per company: name + at least one of (industry, size, location, description).

### Step 3: Score Each Company

For each company, score against the ICP scorecard:

**Grading:**
| Grade | Meaning | Action |
|-------|---------|--------|
| **A** | Strong ICP match (≥80%) | Prioritize outreach |
| **B** | Partial match (50-79%) | Outreach if capacity allows |
| **C** | Weak match (30-49%) | Low priority |
| **D** | Poor match or disqualified (<30%) | Skip |

**For each company, provide:**
- Grade (A/B/C/D)
- Score (0-100)
- 1-line rationale (why this grade)

### Step 4: Output

Generate a prioritized list:

```
## A-Grade (Prioritize) — X companies
| Company | Score | Rationale |
|---------|-------|-----------|
| Acme Corp | 92 | Series B fintech, 200 employees, US-based |

## B-Grade (Secondary) — X companies
...

## Summary
- Total scored: X
- A-grade: X (X%)
- B-grade: X (X%)
- Skipped: X
```

### Optional: Email Verification

If user wants to verify email deliverability:

1. **MX Record check** — verify the domain has a mail server
2. Flag domains with no MX record as likely bounce
3. Common disposable email domains → flag

Note: Full SMTP verification requires running a Python script. Offer to generate the script if needed.

## Key Principles

- **ICP-first**: Define the ideal customer BEFORE scoring. Never score without a rubric.
- **Transparent scoring**: Every grade must have a rationale. No black boxes.
- **Honest about gaps**: If data is missing, say "insufficient data" not guess a score.
- **CRM geography ≠ actual geography**: Registration country often differs from where a company actually operates. Don't over-index on CRM country fields.

## Language

- Supports English and Chinese input/output
- Auto-detect language from user input

---

*Built by Mu Chen · CEO @ Canopy Cloud*
