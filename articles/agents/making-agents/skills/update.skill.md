---
name: update
type: skill
about: Updates an existing agent's frontmatter fields.
---

# Update Agent

Updates frontmatter fields on an existing agent file.

**Arguments:**
- `name` — agent name to update
- `field` — field to change (description, tools, color, etc.)
- `value` — new value

**Behavior:**
1. Finds `agents/<name>.md`
2. Updates the specified frontmatter field
3. Returns confirmation
