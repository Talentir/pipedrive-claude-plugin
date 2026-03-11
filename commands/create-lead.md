---
description: Create a new lead in Pipedrive with title, contact, and optional value
argument-hint: "<lead title and details>"
---

# /create-lead

Create a new lead in Pipedrive CRM.

## Usage

```
/create-lead [lead title and details]
```

Create lead: $ARGUMENTS

---

## Steps

1. **Parse the request** — Extract lead title, contact name, organization, value, and labels from input
2. **Find linked records** — If a contact or organization name is mentioned:
   - Use `search_persons` to find the person and get their `id`
   - Use `search_organizations` to find the org and get their `id`
   - If not found, ask if user wants to create them first
3. **Check labels** — Use `get_lead_labels` to list available labels if the user wants to categorize
4. **Confirm before creating** — Show a summary:
   ```
   Lead: [title]
   Value: $[amount] [currency]
   Contact: [person name] (ID: [id])
   Organization: [org name] (ID: [id])
   Labels: [label names]
   ```
   Ask: "Create this lead?"
5. **Create the lead** — Use `create_lead` with all gathered parameters
6. **Confirm** — Show the created lead with its ID

## Tips

- If user just gives a title, create with minimal info
- Always confirm before creating
- Suggest linking to existing contacts/orgs when possible
- Mention that leads can be converted to deals later with `/convert-lead`
