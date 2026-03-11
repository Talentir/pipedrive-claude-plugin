---
description: Update an existing deal — change stage, value, status, contacts, or any field
argument-hint: "<deal name and what to change>"
---

# /update-deal

Update an existing deal in Pipedrive.

## Usage

```
/update-deal [deal name and what to change]
```

Update deal: $ARGUMENTS

---

## Steps

1. **Find the deal** — Use `search_deals` with the deal name or ID from the user's input
   - If multiple matches, show a brief list and ask which one
   - If no matches, suggest checking the name or listing recent deals
2. **Get current state** — Use `get_deal` to show current deal details
3. **Parse changes** — Determine what the user wants to change. Common updates:
   - **Stage**: Use `get_stages` to find the target stage, then update `stage_id`
   - **Value**: Update `value` and optionally `currency`
   - **Status**: Update to `open`, `won`, or `lost` (with `lost_reason` if lost)
   - **Contact**: Use `search_persons` to find and link via `person_id`
   - **Organization**: Use `search_organizations` to find and link via `org_id`
   - **Owner**: Use `get_users` to find and assign via `user_id`
   - **Expected close date**: Update `expected_close_date` (YYYY-MM-DD)
4. **Confirm before updating** — Show what will change:
   ```
   Deal: [title] (ID: [id])
   Changes:
     [field]: [old value] → [new value]
     [field]: [old value] → [new value]
   ```
   Ask: "Apply these changes?"
5. **Apply update** — Use `update_deal` with the deal ID and changed fields
6. **Confirm** — Show the updated deal summary

## Common Patterns

- "Move [deal] to negotiation" → find stage, update stage_id
- "Mark [deal] as won" → update status to 'won'
- "[Deal] is now worth 50k" → update value
- "Add [person] to [deal]" → search person, update person_id
- "Push [deal] close date to next month" → update expected_close_date
