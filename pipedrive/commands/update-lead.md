---
description: Update an existing lead — change title, value, labels, or linked contacts
argument-hint: "<lead name and what to change>"
---

# /update-lead

Update an existing lead in Pipedrive.

## Usage

```
/update-lead [lead name and what to change]
```

Update lead: $ARGUMENTS

---

## Steps

1. **Find the lead** — Use `search_leads` with the lead name from user's input
   - If multiple matches, show a brief list and ask which one
   - If no matches, suggest checking the name or listing recent leads
2. **Get current state** — Use `get_lead` to show current lead details
3. **Parse changes** — Determine what the user wants to change:
   - **Title**: Update `title`
   - **Value**: Update `value` (object with `amount` and `currency`)
   - **Contact**: Use `search_persons` to find and link via `person_id`
   - **Organization**: Use `search_organizations` to find and link via `organization_id`
   - **Labels**: Use `get_lead_labels` to find label IDs, update `label_ids`
   - **Expected close date**: Update `expected_close_date` (YYYY-MM-DD)
4. **Confirm before updating** — Show what will change:
   ```
   Lead: [title] (ID: [id])
   Changes:
     [field]: [old value] → [new value]
   ```
   Ask: "Apply these changes?"
5. **Apply update** — Use `update_lead` with the lead ID and changed fields
6. **Confirm** — Show the updated lead summary

## Common Patterns

- "Rename lead to ..." → update title
- "Set lead value to 10k" → update value
- "Add [person] to [lead]" → search person, update person_id
- "Label [lead] as hot" → find label, update label_ids
- "Convert [lead] to deal" → suggest using `convert_lead_to_deal` instead
