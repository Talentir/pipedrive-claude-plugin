# Pipedrive Plugin for Claude Code

Connect Claude Code to your Pipedrive CRM. Manage deals, contacts, leads, organizations, activities, and pipeline — all from your terminal.

## Installation

```bash
claude plugin add Talentir/pipedrive-claude-plugin
```

Then set your Pipedrive API token:

```bash
export PIPEDRIVE_API_TOKEN="your_token_here"
```

Find your token in Pipedrive: **Settings > Personal preferences > API**.

Your token never leaves your machine — it's sent as a Bearer token per-request and is not stored on the server.

## Commands

| Command | Description |
|---------|-------------|
| `/create-deal` | Create a new deal with contacts, value, and stage |
| `/update-deal` | Update a deal — stage, value, status, contacts |
| `/create-lead` | Create a new lead with contacts, value, and labels |
| `/update-lead` | Update a lead — title, value, labels, contacts |
| `/create-contact` | Create a new contact with email, phone, and organization |
| `/update-contact` | Update a contact — name, email, phone, organization |
| `/deal-summary` | Get detailed summary of a deal or recent deals |
| `/pipeline-review` | Review pipeline health with actionable recommendations |
| `/quarterly-report` | Generate quarterly sales performance report |

## Skills (Auto-triggered)

| Skill | Triggers On |
|-------|-------------|
| Deal Management | "create a deal", "update deal", "move deal to..." |
| Lead Management | "create a lead", "update lead", "convert lead" |
| Contact Lookup | "find contact", "who is", "look up..." |
| Pipeline Analysis | "how's the pipeline", "forecast", "sales metrics" |

## Available MCP Tools

**Deals:** get_deals, get_deal, search_deals, create_deal, update_deal, delete_deal + batch ops
**Leads:** get_leads, get_lead, search_leads, create_lead, update_lead, delete_lead, convert_lead_to_deal
**Contacts:** get_persons, get_person, search_persons, create_person, update_person, delete_person + batch ops
**Organizations:** get_organizations, get_organization, search_organizations, create/update/delete + batch ops
**Activities:** get_activities, get_activity, create_activity, update_activity, delete_activity, mark_activity_done + batch ops
**Notes:** get_notes, get_note, create_note, update_note, delete_note + batch ops
**Pipelines:** get_pipelines, get_pipeline, get_stages, get_stage, create/update/delete pipeline and stage
**Search:** search_items (cross-entity search)
**Users:** get_users, get_user, get_current_user

All list endpoints support `sort` (e.g. `"add_time DESC"`), pagination, and filtering.

## How It Works

This plugin connects to a hosted MCP server on Vercel that proxies requests to the Pipedrive API. Your API token is passed as a Bearer token in each request — the server is stateless and stores nothing.

## License

MIT
