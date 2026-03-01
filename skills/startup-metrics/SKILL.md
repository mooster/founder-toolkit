---
name: startup-metrics
description: This skill should be used when the user asks to "calculate startup metrics", "SaaS metrics", "calculate ARR", "burn multiple", "runway calculator", "magic number", "unit economics", "LTV CAC ratio", "quick ratio", "NRR", "net revenue retention", or wants to compute and analyze key business metrics from raw company data. Provides full SaaS metric calculations with benchmark context.
---

# Startup Metrics Dashboard

Calculate the full suite of SaaS/startup metrics from raw numbers. Provides benchmark context so metrics are not just numbers in a vacuum.

## Process

### Step 1: Gather Raw Data

Collect available data from the user. Not all fields are required — compute everything derivable from what is provided.

**Core inputs:**
- Monthly Recurring Revenue (MRR) — current and 1-2 prior months
- Number of customers (new, churned, total)
- Monthly operating expenses / burn rate
- Cash in bank

**For deeper analysis (optional):**
- Revenue breakdown: new MRR, expansion MRR, churned MRR, contraction MRR
- Sales & marketing spend (for CAC, magic number)
- Average revenue per account (ARPA)
- Gross margin percentage

Do not ask for values that can be derived. Calculate automatically when possible.

### Step 2: Compute Metrics

Calculate all metrics derivable from the inputs. For complete formulas and definitions, consult `references/formulas.md`.

**Core metrics to always include (when data allows):**

| Category | Metrics |
|----------|---------|
| Growth | ARR, MoM growth, QoQ growth, Net new MRR |
| Retention | Gross churn, NRR, Logo retention, Quick Ratio |
| Unit Economics | ARPA, CAC, LTV, LTV:CAC, CAC payback |
| Efficiency | Burn rate, Burn multiple, Runway, Magic Number, Rule of 40 |

### Step 3: Output Dashboard

```
## Startup Metrics Dashboard — [Month Year]

### At a Glance
| Metric | Value | Benchmark | Status |
|--------|-------|-----------|--------|
| ARR | $X | — | — |
| MoM Growth | X% | >10% (early) / >5% (scale) | [good/watch/concern] |
| NRR | X% | >110% | [good/watch/concern] |
| Burn Multiple | X.Xx | <2x | [good/watch/concern] |
| Runway | X mo | >12 mo | [good/watch/concern] |
| LTV:CAC | X.Xx | >3x | [good/watch/concern] |

### Detailed Metrics
[Grouped by category with MoM comparison when available]

### Key Takeaways
1. [Most important insight — what's working]
2. [Most important concern — what needs attention]
3. [Recommended focus area]
```

### Step 4: Benchmark Context

For each metric, provide context on what "good" looks like. Consult `references/benchmarks.md` for the full benchmark table by stage.

Flag metrics below benchmark as areas for attention. Acknowledge metrics above benchmark as strengths.

### Multi-Period Tracking

When the user provides data for multiple months:
- Show trends (improving / declining / stable)
- Calculate 3-month rolling averages for volatile metrics
- Highlight significant MoM changes (>20% swing)

## Language

- Default to English
- When user inputs in Chinese, output in Chinese
- Metric names remain in English (ARR, NRR, LTV, CAC are industry standard)

## Scope Boundaries

This skill calculates and analyzes metrics. It does NOT:
- Make financial forecasts or projections
- Estimate company valuations
- Provide accounting or tax advice

## Additional Resources

### Reference Files

- **`references/formulas.md`** — Complete formula definitions for all metrics, with derivation notes and edge case handling.
- **`references/benchmarks.md`** — Benchmark tables by company stage (early, growth, scale) for all supported metrics.
