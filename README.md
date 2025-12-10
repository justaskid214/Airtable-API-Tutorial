# Airtable API Tutorial

Simple tutorial for integrating the Airtable API into your projects.

## 1) Get a Personal Access Token (PAT)
- In Airtable, go to Account → Developer Hub → Personal Access Tokens.
- Create a token with scopes: `data.records:read`, `data.records:write`, `metadata:read`.
- Add the bases this token should access.
- Copy the token and keep it secret.

## 2) Find your Base ID
- Open the base you want.
- Click Help → API documentation for this base.
- Copy the Base ID (looks like `appXXXXXXXXXXXXXX`).

## 3) Find your Table ID (recommended) or exact Table Name
- In the base’s API docs, find your table.
- Copy the Table ID (looks like `tblXXXXXXXXXXXXXX`). Using the ID avoids name/spacing issues.
- If you use the name instead, it must match exactly (including spaces and capitalization).

## 4) Test a read request
Replace `YOUR_TOKEN`, `BASE_ID`, `TABLE_ID`:
```
curl -H "Authorization: Bearer YOUR_TOKEN" \
     "https://api.airtable.com/v0/BASE_ID/TABLE_ID?maxRecords=1"
```
- If you get records, access works.
- If 403, check scopes or whether the token owner is a collaborator on the base.
- If 404, check the base/table ID.

## 5) Create a record
```
curl -X POST \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"records":[{"fields":{"Field1":"Value","Field2":123}}]}' \
  "https://api.airtable.com/v0/BASE_ID/TABLE_ID"
```

## Good habits
- Prefer table IDs over names to avoid typos/spaces issues.
- Store tokens in environment variables, not in code.
- Make sure the token owner is invited to the base with editor-level access.
- Always do a quick GET test before wiring into apps.
