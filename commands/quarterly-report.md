---
description: Generate a quarterly sales performance report with metrics, trends, and forecasting
argument-hint: "<quarter like Q1, Q2, or 'current'>"
---

# /quarterly-report

Generate a comprehensive quarterly sales report.

## Usage

```
/quarterly-report [quarter]
```

Generate report for: $ARGUMENTS

---

## Steps

1. Use `get_quarter_summary` with the specified quarter
2. Use `get_quarterly_progress` for current quarter forecasting
3. Use `get_deals_summary` to get deal details
4. Calculate trends and present analysis

## Output Format

```markdown
# Quarterly Report: [Q# YYYY]

## Key Metrics
| Metric | Value |
|--------|-------|
| Total Deals | [X] |
| Total Value | $[X] |
| Won Deals | [X] ($[X]) |
| Lost Deals | [X] |
| Win Rate | [X]% |
| Open Pipeline | $[X] |

## Top Deals
[Top 5 deals by value]

## Stage Breakdown
[Deals per stage with value]

## Trends & Observations
[Analysis of patterns]

## Forecast
[Projected close rate and revenue for remainder of quarter]

## Recommendations
[Actions to improve performance]
```
