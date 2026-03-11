---
description: Get a quick summary of a specific deal or all recent deals
argument-hint: "<deal name, ID, or 'recent'>"
---

# /deal-summary

Get a comprehensive summary of a deal or your recent deals.

## Usage

```
/deal-summary [deal name, ID, or 'recent']
```

Summarize: $ARGUMENTS

---

## Steps

### For a specific deal:
1. Use `search_deals` with the provided term to find the deal
2. Use `get_deal` with the ID for full details
3. Use `get_notes` filtered by deal_id for context
4. Use `get_activities` filtered to find related activities
5. Present a comprehensive summary

### For recent deals:
1. Use `get_deals_summary` for a token-optimized overview
2. Highlight deals closing this month
3. Flag any requiring attention

## Output Format

```markdown
# Deal: [Title]

| Field | Value |
|-------|-------|
| **Value** | $[amount] [currency] |
| **Stage** | [stage name] |
| **Pipeline** | [pipeline name] |
| **Owner** | [user name] |
| **Created** | [date] |
| **Expected Close** | [date] |
| **Probability** | [%] |

## Contact
[Person name, org, email, phone]

## Recent Activity
[Last 5 activities]

## Notes
[Recent notes summary]

## Suggested Next Steps
[Based on stage and activity patterns]
```
