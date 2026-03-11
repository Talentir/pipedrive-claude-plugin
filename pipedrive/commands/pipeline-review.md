---
description: Review your Pipedrive pipeline — deal health, stage distribution, stale deals, and action items
argument-hint: "<pipeline name or 'all'>"
---

# /pipeline-review

Review pipeline health and get actionable recommendations.

## Usage

```
/pipeline-review [pipeline name or 'all']
```

Review pipeline for: $ARGUMENTS

---

## Steps

1. **Get pipeline overview** — Use `get_pipelines` and `get_stages` to understand the pipeline structure
2. **Pull deals** — Use `get_deals` to get all open deals, or filter by pipeline
3. **Analyze health:**
   - Flag deals with no activity in 14+ days (stale)
   - Flag deals stuck in same stage 30+ days
   - Flag deals with close dates in the past
   - Identify single-threaded deals (only one contact)
4. **Calculate metrics:**
   - Total pipeline value
   - Deals per stage
   - Average deal age
   - Win rate from `get_quarter_summary`
5. **Prioritize** — Rank deals by: close date (30%), deal size (25%), stage (20%), activity recency (15%), risk (10%)
6. **Output** — Present in the format below

## Output Format

```markdown
# Pipeline Review: [Date]

## Pipeline Health Score: [X/100]

| Dimension | Score | Issue |
|-----------|-------|-------|
| Stage Progression | /25 | deals stuck 30+ days |
| Activity Recency | /25 | deals silent 14+ days |
| Close Date Accuracy | /25 | deals with past close dates |
| Deal Coverage | /25 | single-threaded deals |

## Priority Deals This Week
[Top 5 deals ranked by priority with specific next actions]

## Risk Flags
[Stale, stuck, overdue, and single-threaded deals]

## Stage Distribution
[Deals and value per stage]

## Recommendations
[3-5 specific actions for this week]
```
