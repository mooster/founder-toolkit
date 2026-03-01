# Founder Toolkit

Essential Claude Code skills for startup founders. Built from real operational experience running a $120B+ AUM fintech, not theory.

## Skills

| Skill | What it does | Language |
|-------|-------------|---------|
| **investor-update** | Generate professional investor monthly/quarterly updates (YC/a16z format) | EN / 中文 |
| **pitch-reviewer** | Review pitch decks with structured VC-perspective scoring (10 dimensions, 1-5 each) | EN |
| **startup-metrics** | Calculate full SaaS metrics suite (ARR, NRR, LTV, CAC, burn multiple, runway, etc.) with benchmark context | EN / 中文 |
| **lead-scorer** | Score and prioritize outreach leads using ICP-first methodology | EN / 中文 |

## Install

```bash
/plugin marketplace add mooster/founder-toolkit
/plugin install founder-toolkit@mooster-founder-toolkit
```

## Usage

Skills activate automatically when Claude detects relevant context:

- "Write an investor update" → `investor-update`
- "Review my pitch deck" → `pitch-reviewer`
- "Calculate our SaaS metrics" → `startup-metrics`
- "Score these leads" → `lead-scorer`

## What's Inside

Each skill includes detailed reference materials, not just prompts:

- **Investor Update**: Complete format guide, subject line patterns, tone calibration, anti-patterns
- **Pitch Reviewer**: 10-dimension scoring rubric (1-5 each), stage-calibrated expectations (pre-seed → Series B+), common mistakes per dimension
- **Startup Metrics**: Full formula definitions with edge cases (negative churn, infinite LTV), benchmarks from OpenView/Bessemer/SaaStr by stage
- **Lead Scorer**: ICP-weighted scorecard, A/B/C/D grading with mandatory rationale, 3-layer email deliverability verification (tested on 8,000+ contacts)

## Built By

**Mu Chen** · CEO @ [Canopy Cloud](https://canopycloud.com) · 60+ institutional clients · $120B+ AUM

These skills encode real operational knowledge from running a wealth management platform. The lead scorer is based on a production system that evaluated 300+ companies. The metrics dashboard includes every edge case we've hit.

## License

MIT
