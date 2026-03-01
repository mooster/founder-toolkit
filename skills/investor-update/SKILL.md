---
name: investor-update
description: Generate professional investor monthly or quarterly updates for startup founders. Use when user mentions "investor update", "investor letter", "monthly update to investors", "quarterly update", "投资人月报", "给投资人写 update", or wants to communicate progress to investors/board.
---

# Investor Update Writer

Generate concise, professional investor updates that keep your investors informed and engaged. Follows best practices from YC, a16z, and top VC firms.

## Process

### Step 1: Gather Key Data

Ask the user for these inputs (skip any they don't have):

**Required:**
- MRR or ARR (and previous period for comparison)
- Cash balance and monthly burn rate
- 2-3 highlights from this period
- 1-2 challenges or asks

**Optional (auto-calculate if possible):**
- Customer count (new, churned, total)
- Runway (= cash / burn)
- Key hires or team changes
- Product milestones
- Fundraising status

**Do NOT ask for things you can calculate.** If they give you cash ($500K) and burn ($50K/mo), runway is 10 months — just calculate it.

### Step 2: Generate the Update

Use this structure:

```
Subject: [Company Name] — [Month Year] Investor Update

Hi [investors / team],

## TL;DR
[3 sentences max. Lead with the most important news. Be honest — if it was a tough month, say so.]

## Key Metrics

| Metric | This Month | Last Month | Change |
|--------|-----------|------------|--------|
| MRR | $XX | $XX | +X% |
| Customers | XX | XX | +X |
| Burn | $XX/mo | $XX/mo | — |
| Runway | XX months | — | — |
| [Custom] | XX | XX | +X% |

## Highlights
- [Concrete achievement with numbers]
- [Concrete achievement with numbers]

## Challenges
- [Honest assessment — not sugarcoated, not catastrophized]

## Asks
[Specific, actionable requests. "Intro to VP Engineering at X" not "help with hiring".]

## What's Next
- [2-3 priorities for next period]

Best,
[Name]
```

### Step 3: Tone Check

Before outputting, verify:

- **Honest but not dramatic** — "Growth slowed to 5% as we focused on retention" not "We're struggling"
- **Specific not vague** — Numbers, names, dates. Not "things are going well"
- **Concise** — Investors read dozens of these. Entire update should be <500 words
- **Asks are actionable** — "Can you intro us to [specific person/company]?" not "We need help with sales"
- **No jargon dumping** — Write for a smart generalist, not a domain expert

## Language

- Default to English
- If user inputs in Chinese, output in Chinese with the same structure
- Metric names stay in English even in Chinese updates (ARR, MRR, NRR are universal)

## Anti-patterns to Avoid

- Don't pad with fluff ("We're excited to share...")
- Don't hide bad news — investors respect honesty and lose trust when surprised
- Don't make it longer than necessary — if it's a quiet month, a short update is fine
- Don't include vanity metrics without context (page views without conversion)
- Don't ask for "advice" generically — ask for specific intros or specific help

---

*Built by Mu Chen · CEO @ Canopy Cloud*
