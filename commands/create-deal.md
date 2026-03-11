---
description: Create a new deal in Pipedrive with contacts, value, and pipeline stage
argument-hint: "<deal title and details>"
---

# /create-deal

Create a new deal in Pipedrive CRM.

## Usage

```
/create-deal [deal title and details]
```

Create deal: $ARGUMENTS

---

## Steps

1. **Parse the request** — Extract deal title, value, contact name, organization, pipeline, and stage from the user's input
2. **Find linked records** — If a contact or organization name is mentioned:
   - Use `search_persons` to find the person and get their `id`
   - Use `search_organizations` to find the org and get their `id`
   - If not found, ask if user wants to create them first
3. **Resolve pipeline/stage** — If a stage or pipeline is mentioned:
   - Use `get_pipelines` to list available pipelines
   - Use `get_stages` to find the right stage
   - If not specified, use the first stage of the default pipeline
4. **Confirm before creating** — Show a summary of what will be created:
   ```
   Deal: [title]
   Value: $[amount] [currency]
   Contact: [person name] (ID: [id])
   Organization: [org name] (ID: [id])
   Pipeline: [pipeline name] → Stage: [stage name]
   ```
   Ask: "Create this deal?"
5. **Create the deal** — Use `create_deal` with all gathered parameters
6. **Confirm** — Show the created deal with its ID and a link

## Tips

- If user just gives a title, create with minimal info and let them fill in details later
- Always confirm before creating
- Suggest linking to existing contacts/orgs when possible
