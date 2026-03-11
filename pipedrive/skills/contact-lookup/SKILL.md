---
name: contact-lookup
description: Look up contacts and organizations in Pipedrive. Triggers on "find contact", "look up", "who is", "find person", "search for", "contact info for".
---

# Contact Lookup

Help users find and view contact and organization information in Pipedrive.

## When This Triggers

- User asks to find a person or organization
- User asks "who is [name]"
- User needs contact details

## How It Works

1. Use `search_persons` or `search_organizations` with the user's query
2. If multiple results, show a brief list and ask which one
3. Use `get_person` or `get_organization` for full details
4. Use `get_deals` filtered by person_id or org_id to show related deals
5. Present contact info with related context

## Output

Show: name, email, phone, organization, related deals (with values and stages), recent activities
