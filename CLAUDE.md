# CLAUDE.md

## Project Overview

This is a **documentation-only** repository containing a quick-start guide for integrating the Airtable API. There is no application code, no dependencies, and no build process — the entire project consists of Markdown files.

## Repository Structure

```
Airtable-API-Tutorial/
├── README.md   # The tutorial (only content file)
└── CLAUDE.md   # This file
```

## Content

`README.md` is a concise, step-by-step Airtable API tutorial covering:

1. Creating a Personal Access Token (PAT) with the required scopes (`data.records:read`, `data.records:write`, `metadata:read`)
2. Locating the Base ID (`appXXXXXXXXXXXXXX` format)
3. Locating the Table ID (`tblXXXXXXXXXXXXXX` format) — preferred over table names
4. Testing read requests with `curl`
5. Creating records via POST
6. Best practices (use IDs not names, store tokens in env vars, require editor-level access)

## Development Workflow

Since there is no code, the only workflow is editing Markdown.

```bash
# Check out the feature branch
git checkout claude/claude-md-docs-dtGsZ

# Edit files
# (use Read/Edit tools or your editor)

# Commit and push
git add README.md CLAUDE.md
git commit -m "describe what changed"
git push -u origin claude/claude-md-docs-dtGsZ
```

**Default development branch:** `claude/claude-md-docs-dtGsZ`  
**Main branch:** `main`

## Conventions

- Write in plain, concise English — this is a developer quick-reference, not an essay.
- Use numbered sections (`## 1) ...`) to keep steps scannable.
- Use inline code formatting for all identifiers, IDs, scope strings, and CLI flags.
- Prefer Table IDs over table names in all examples (avoids spacing/capitalization bugs).
- Never embed real tokens, Base IDs, or Table IDs — use `YOUR_TOKEN`, `BASE_ID`, `TABLE_ID` as placeholders.
- Keep curl examples copy-paste ready (all on one logical command, backslash-continued for readability).
- Do not add a build system, package manager, or dependencies — this repo intentionally has none.

## What Not to Do

- Do not add source code, scripts, or tooling unless the scope of the project explicitly changes.
- Do not commit `.env` files or any file containing real credentials.
- Do not push directly to `main` — use the feature branch and open a PR.
