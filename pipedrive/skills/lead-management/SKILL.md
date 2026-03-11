---
name: lead-management
description: Manage Pipedrive leads — create, update, convert to deals, and track progress. Triggers on "create a lead", "update lead", "new lead", "convert lead", "lead labels".
---

# Lead Management

Help users manage their Pipedrive leads efficiently.

## When This Triggers

- User asks to create, update, or manage leads
- User mentions lead names, values, or labels
- User wants to convert a lead to a deal

## How It Works

### Creating Leads
1. Ask for required info: lead title
2. Ask for optional info: value, currency, contact, organization, labels
3. Use `search_persons` or `search_organizations` to find linked records if names are given
4. Use `get_lead_labels` to resolve label names to IDs if labels are mentioned
5. Use `create_lead` with all gathered info
6. Confirm creation with lead details

### Updating Leads
1. Use `search_leads` to find the lead by name
2. Show current details using `get_lead`
3. Apply requested changes using `update_lead`
4. Confirm what was changed

### Converting Leads to Deals
1. Find the lead with `search_leads`
2. Show current lead details
3. Ask which pipeline/stage to place the new deal in (use `get_pipelines` and `get_stages`)
4. Use `convert_lead_to_deal` to convert
5. Show the new deal details

### Best Practices
- Always confirm before creating or modifying data
- Show the user what will change before applying updates
- When creating leads, suggest linking to existing contacts/orgs
- Mention conversion to deal as a next step when appropriate
