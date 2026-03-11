---
description: Create a new contact (person) in Pipedrive with email, phone, and organization
argument-hint: "<contact name and details>"
---

# /create-contact

Create a new contact in Pipedrive CRM.

## Usage

```
/create-contact [contact name and details]
```

Create contact: $ARGUMENTS

---

## Steps

1. **Parse the request** — Extract name, email, phone, and organization from the user's input
2. **Check for duplicates** — Use `search_persons` with the name to see if they already exist
   - If found, show the match and ask if user wants to update instead
3. **Find linked organization** — If an organization name is mentioned:
   - Use `search_organizations` to find it and get the `org_id`
   - If not found, ask if user wants to create the org first
4. **Confirm before creating** — Show a summary:
   ```
   Name: [name]
   Email: [email]
   Phone: [phone]
   Organization: [org name] (ID: [id])
   ```
   Ask: "Create this contact?"
5. **Create the contact** — Use `create_person` with all gathered parameters
6. **Confirm** — Show the created contact with their ID

## Tips

- If user just gives a name, create with minimal info
- Always check for duplicates first
- Suggest linking to an existing organization when possible
