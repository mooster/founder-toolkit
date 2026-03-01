---
name: startup-metrics
description: Calculate and analyze SaaS/startup metrics from raw data — ARR, growth, NRR, LTV, CAC, burn multiple, runway, magic number, and more. Use when user mentions "startup metrics", "SaaS metrics", "calculate ARR", "burn multiple", "runway", "magic number", "unit economics", "LTV CAC", "quick ratio", "NRR", "net revenue retention", or wants to analyze their company's key metrics.
---

# Startup Metrics Dashboard

Calculate the full suite of SaaS/startup metrics from raw numbers. No spreadsheet needed.

## Process

### Step 1: Gather Raw Data

Ask user for available data. Not all fields are required — calculate what's possible from what's given.

**Core inputs:**
- Monthly Recurring Revenue (MRR) — current and 1-2 prior months
- Number of customers (new, churned, total)
- Monthly operating expenses / burn
- Cash in bank

**For deeper analysis (optional):**
- Revenue breakdown: new MRR, expansion MRR, churned MRR, contraction MRR
- Sales & marketing spend
- Average deal size / ARPA
- Customer acquisition details (leads, conversion rate)

### Step 2: Calculate Metrics

Compute everything derivable from the inputs. Use these formulas:

#### Growth Metrics
| Metric | Formula |
|--------|---------|
| ARR | MRR × 12 |
| MoM Growth | (MRR_current - MRR_previous) / MRR_previous |
| QoQ Growth | (MRR_current - MRR_3mo_ago) / MRR_3mo_ago |
| Net New MRR | New + Expansion - Churned - Contraction |

#### Retention Metrics
| Metric | Formula |
|--------|---------|
| Gross Churn Rate | Churned MRR / Starting MRR |
| Net Revenue Retention (NRR) | (Starting MRR - Churned - Contraction + Expansion) / Starting MRR |
| Logo Retention | 1 - (Churned customers / Starting customers) |
| Quick Ratio | (New MRR + Expansion MRR) / (Churned MRR + Contraction MRR) |

#### Unit Economics
| Metric | Formula |
|--------|---------|
| ARPA | MRR / Total customers |
| CAC | S&M spend / New customers acquired |
| LTV | ARPA / Monthly gross churn rate |
| LTV:CAC | LTV / CAC |
| Months to recover CAC | CAC / (ARPA × Gross margin) |

#### Efficiency Metrics
| Metric | Formula |
|--------|---------|
| Burn Multiple | Net burn / Net new ARR |
| Monthly Burn | Total expenses - Total revenue |
| Runway | Cash / Monthly burn |
| Magic Number | (QoQ ARR change) / (Prior quarter S&M spend) |
| Rule of 40 | Revenue growth % + Profit margin % |

### Step 3: Output Dashboard

```
## Startup Metrics Dashboard — [Month Year]

### At a Glance
| Metric | Value | Benchmark | Status |
|--------|-------|-----------|--------|
| ARR | $X | — | — |
| MoM Growth | X% | >10% (early) / >5% (scale) | [flag] |
| NRR | X% | >110% | [flag] |
| Burn Multiple | X.Xx | <2x good, <1x great | [flag] |
| Runway | X months | >12 months | [flag] |
| LTV:CAC | X.Xx | >3x | [flag] |

### Growth
[Detailed growth metrics with MoM trend]

### Retention
[Detailed retention metrics]

### Unit Economics
[CAC, LTV, payback period]

### Efficiency
[Burn, magic number, rule of 40]

### Key Takeaways
1. [Most important insight]
2. [Second insight]
3. [What to focus on improving]
```

### Step 4: Benchmark Context

For each metric, provide context on what "good" looks like:

| Metric | Early Stage | Growth Stage | Scale |
|--------|------------|-------------|-------|
| MoM Growth | >15% | >10% | >5% |
| NRR | >100% | >110% | >120% |
| Gross Churn | <5% | <3% | <2% |
| LTV:CAC | >3x | >4x | >5x |
| Burn Multiple | <3x | <2x | <1.5x |
| Quick Ratio | >4x | >3x | >2x |
| CAC Payback | <18mo | <12mo | <9mo |
| Magic Number | >0.5 | >0.75 | >1.0 |
| Rule of 40 | N/A | >40% | >40% |

**Flag** metrics that are below benchmark as areas for attention. **Celebrate** metrics that are above benchmark.

## Multi-Period Tracking

If user provides data for multiple months:
- Show trends (improving / declining / stable)
- Calculate 3-month rolling averages for volatile metrics
- Highlight significant MoM changes (>20% swing)

## Language

- Default to English
- If user inputs in Chinese, output in Chinese
- Metric names always in English (ARR, NRR, LTV, CAC are industry standard)

## What This Skill Does NOT Do

- Financial forecasting or projections (too many assumptions)
- Valuation estimates (depends on market conditions)
- Accounting advice (talk to your accountant)

---

*Built by Mu Chen · CEO @ Canopy Cloud*
