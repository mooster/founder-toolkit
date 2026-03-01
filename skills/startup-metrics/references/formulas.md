# Startup Metrics Formulas

Complete formula definitions for all supported metrics.

## Growth Metrics

| Metric | Formula | Notes |
|--------|---------|-------|
| ARR | MRR × 12 | Annualized run rate, not trailing 12-month revenue |
| MoM Growth | (MRR_current - MRR_previous) / MRR_previous | Express as percentage |
| QoQ Growth | (MRR_current - MRR_3months_ago) / MRR_3months_ago | More stable than MoM |
| Net New MRR | New MRR + Expansion MRR - Churned MRR - Contraction MRR | Core growth driver |
| YoY Growth | (ARR_current - ARR_12months_ago) / ARR_12months_ago | Best for mature companies |

## Retention Metrics

| Metric | Formula | Notes |
|--------|---------|-------|
| Gross Revenue Churn | Churned MRR / Starting MRR | Revenue lost, ignoring expansion |
| Net Revenue Retention (NRR) | (Starting MRR - Churn - Contraction + Expansion) / Starting MRR | >100% means existing customers grow |
| Logo (Customer) Retention | 1 - (Churned customers / Starting customers) | Count-based, not revenue-weighted |
| Quick Ratio | (New MRR + Expansion MRR) / (Churned MRR + Contraction MRR) | Measures growth efficiency. >4 excellent, <2 concerning |

## Unit Economics

| Metric | Formula | Notes |
|--------|---------|-------|
| ARPA | MRR / Total customers | Average Revenue Per Account |
| CAC | Total S&M spend / New customers acquired | Customer Acquisition Cost |
| LTV | ARPA / Monthly gross churn rate | Lifetime Value. Use gross margin-adjusted ARPA for accuracy |
| LTV:CAC | LTV / CAC | Payback ratio. >3x is healthy |
| CAC Payback (months) | CAC / (ARPA × Gross margin %) | Months to recover acquisition cost |

## Efficiency Metrics

| Metric | Formula | Notes |
|--------|---------|-------|
| Monthly Burn | Total expenses - Total revenue | Net cash consumed per month |
| Burn Multiple | Net burn / Net new ARR | How much burned per dollar of new ARR. <1x excellent |
| Runway (months) | Cash balance / Monthly burn | Months until cash runs out |
| Magic Number | QoQ Net new ARR / Prior quarter S&M spend | S&M efficiency. >1.0 means increase S&M spend |
| Rule of 40 | Revenue growth % + Profit margin % | >40% is the target for healthy SaaS |

## Edge Cases

- **Negative churn (NRR > 100%):** Expansion exceeds churn. Common in strong PLG or enterprise models. Highlight as a strength.
- **Infinite LTV:** When monthly churn is 0%, LTV is technically infinite. Cap at 60-month LTV for practical reporting.
- **Negative burn:** Company is profitable. Runway is infinite. Report as "Cash flow positive."
- **No S&M data:** Cannot calculate CAC, LTV:CAC, or Magic Number. Note as "insufficient data" rather than omitting silently.
- **Single month data:** Cannot compute growth rates or trends. Report current values only and note that trend analysis requires 2+ months.
