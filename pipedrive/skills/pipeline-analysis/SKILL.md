---
name: pipeline-analysis
description: Analyze pipeline health, deal velocity, and sales forecasting. Triggers on "how's the pipeline", "pipeline health", "forecast", "deal velocity", "sales metrics", "how are we doing".
---

# Pipeline Analysis

Provide sales pipeline analysis and forecasting from Pipedrive data.

## When This Triggers

- User asks about pipeline health or status
- User asks for sales metrics or forecasting
- User asks "how are we doing" or similar

## How It Works

1. Use `get_overview` for a quick high-level view
2. Use `get_pipelines` and `get_stages` for structure
3. Use `get_deals_summary` for deal data
4. Use `get_quarter_summary` for quarterly metrics
5. Calculate: stage distribution, deal velocity, conversion rates, projected revenue
6. Present analysis with actionable insights

## Key Metrics to Surface

- Total pipeline value (open deals)
- Weighted pipeline (value x probability)
- Deals by stage (count and value)
- Win rate (won / total closed)
- Average deal cycle time
- Stale deals (no activity 14+ days)
- Quarter progress vs target
