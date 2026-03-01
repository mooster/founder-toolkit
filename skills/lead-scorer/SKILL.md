---
name: lead-scorer
description: This skill should be used when the user asks to "score leads", "qualify companies", "prioritize outreach", "lead scoring", "ICP matching", "grade prospects", "评分", "打分", "outreach list", or wants to evaluate and rank companies for sales or business development outreach. Implements ICP-first scoring methodology.
---

# Outreach Lead Scorer

Score and prioritize companies for outreach using an ICP-first methodology. Based on a production system that evaluated 300+ companies.

## Process

### Step 1: Define the ICP (Ideal Customer Profile)

Before scoring any company, define the rubric. Help the user think through:

- **Industry**: Target verticals (e.g., fintech, SaaS, healthcare)
- **Size**: Employee count or revenue range
- **Geography**: Target regions
- **Key signals**: What makes a company especially good (e.g., recent funding, specific tech stack, regulatory need)
- **Disqualifiers**: What makes a company a bad fit (e.g., too small, wrong vertical, competitor)

Output the ICP as a weighted scorecard:

```
ICP Scorecard:
- Industry match: [weight X/10]
- Size match: [weight X/10]
- Geography match: [weight X/10]
- Signal 1 (e.g., recent funding): [weight X/10]
- Signal 2 (e.g., tech stack): [weight X/10]
Disqualifiers: [list]
```

Get user confirmation on the scorecard before proceeding to scoring.

### Step 2: Ingest Company Data

Accept input from:
- **CSV/spreadsheet** — parse columns automatically
- **Manual list** — company names with basic info
- **HubSpot** — pull from CRM if HubSpot MCP tools are available

Minimum data per company: name + at least one of (industry, size, location, description).

### Step 3: Score Against the ICP

For each company, evaluate against the scorecard and assign a grade:

| Grade | ICP Match | Action |
|-------|-----------|--------|
| **A** | ≥80% | Prioritize — outreach immediately |
| **B** | 50-79% | Secondary — outreach if capacity allows |
| **C** | 30-49% | Low priority — park for later |
| **D** | <30% or disqualified | Skip |

Provide a 1-line rationale for every grade. No black-box scores.

### Step 4: Output the Prioritized List

```
## A-Grade (Prioritize) — X companies
| Company | Score | Rationale |
|---------|-------|-----------|
| Acme Corp | 92 | Series B fintech, 200 employees, US-based |

## B-Grade (Secondary) — X companies
[...]

## Summary
- Total scored: X
- A-grade: X (X%)
- B-grade: X (X%)
- C-grade: X (X%)
- Skipped: X
```

### Optional: Email Verification

When the user wants to verify email deliverability, consult `references/email-verification.md` for the three-layer verification methodology.

## Key Principles

- **ICP-first**: Define the ideal customer BEFORE scoring. Never score without a rubric.
- **Transparent scoring**: Every grade must have a written rationale. No black boxes.
- **Honest about gaps**: When data is missing, mark as "insufficient data" — do not guess.
- **CRM geography caveat**: Registration country often differs from actual operations. Do not over-index on CRM country fields.

## Language

- Supports English and Chinese input/output
- Auto-detect language from user input and match

## Additional Resources

### Reference Files

- **`references/email-verification.md`** — Three-layer email verification methodology (Syntax → MX → SMTP) with catch-all detection. Consult when the user wants to validate email deliverability.
