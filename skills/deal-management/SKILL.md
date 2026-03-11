---
name: deal-management
description: Manage Pipedrive deals — create, update, move between stages, and track progress. Triggers on "create a deal", "update deal", "move deal to", "add a deal for", "log a deal".
---

# Deal Management

Help users manage their Pipedrive deals efficiently.

## When This Triggers

- User asks to create, update, or manage deals
- User mentions deal names, values, or stages
- User wants to move deals between pipeline stages

## How It Works

### Creating Deals
1. Ask for required info: deal title
2. Ask for optional info: value, currency, contact, organization, pipeline, stage
3. Use `search_persons` or `search_organizations` to find linked records if names are given
4. Use `create_deal` with all gathered info
5. Confirm creation with deal details

### Updating Deals
1. Use `search_deals` to find the deal by name
2. Show current details using `get_deal`
3. Apply requested changes using `update_deal`
4. Confirm what was changed

### Moving Deals
1. Find the deal with `search_deals`
2. Get available stages with `get_stages` for the deal's pipeline
3. Use `update_deal` to change stage_id
4. Confirm the move

### Best Practices
- Always confirm before creating or modifying data
- Show the user what will change before applying updates
- When creating deals, suggest linking to existing contacts/orgs
- After updates, show the updated deal summary
