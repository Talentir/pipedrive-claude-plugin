---
description: Update an existing contact — change name, email, phone, organization, or any field
argument-hint: "<contact name and what to change>"
---

# /update-contact

Update an existing contact in Pipedrive.

## Usage

```
/update-contact [contact name and what to change]
```

Update contact: $ARGUMENTS

---

## Steps

1. **Find the contact** — Use `search_persons` with the name or ID from the user's input
   - If multiple matches, show a brief list and ask which one
   - If no matches, suggest checking the name or listing recent contacts
2. **Get current state** — Use `get_person` to show current contact details
3. **Parse changes** — Determine what the user wants to change:
   - **Name**: Update `name`
   - **Email**: Update `email`
   - **Phone**: Update `phone`
   - **Organization**: Use `search_organizations` to find and link via `org_id`
   - **Owner**: Use `get_users` to find and assign via `owner_id`
   - **Visibility**: Update `visible_to`
4. **Confirm before updating** — Show what will change:
   ```
   Contact: [name] (ID: [id])
   Changes:
     [field]: [old value] → [new value]
   ```
   Ask: "Apply these changes?"
5. **Apply update** — Use `update_person` with the person ID and changed fields
6. **Confirm** — Show the updated contact summary

## Common Patterns

- "Change [person]'s email to x@y.com" → update email
- "Add phone number for [person]" → update phone
- "Move [person] to [org]" → search org, update org_id
- "Rename [person] to [new name]" → update name
