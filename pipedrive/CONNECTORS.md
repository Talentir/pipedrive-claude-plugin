# Connectors

This plugin connects to **Pipedrive CRM** via MCP.

## Pipedrive

| Setting | Value |
|---------|-------|
| **Server** | `pipedrive` in `.mcp.json` |
| **URL** | Your deployed Pipedrive MCP server |
| **Auth** | API token configured on the server |

### Available Tools

**Deals:** get_deals, get_deal, search_deals, create_deal, update_deal, delete_deal, batch operations
**Contacts:** get_persons, get_person, search_persons, create_person, update_person, delete_person, batch operations
**Organizations:** get_organizations, get_organization, search_organizations, create_organization, update_organization, delete_organization, batch operations
**Activities:** get_activities, get_activity, create_activity, update_activity, delete_activity, mark_activity_done, batch operations
**Notes:** get_notes, get_note, create_note, update_note, delete_note, batch operations
**Pipelines:** get_pipelines, get_pipeline, get_stages, get_stage, create/update/delete pipeline and stage
**Search:** search_items (cross-entity)
**Users:** get_users, get_user, get_current_user
**Optimized:** get_deals_summary, get_persons_summary, get_organizations_summary, get_activities_summary, get_overview, search_summarized
**Quarterly:** get_current_quarter_deals, get_quarter_summary, get_quarterly_progress

### Setup

Update the URL in `.mcp.json` to point to your deployed Pipedrive MCP server on Vercel.
