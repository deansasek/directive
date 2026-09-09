---
name: delete
type: skill
about: Removes an agent file from agents/.
---

# Delete Agent

Removes an agent file.

**Arguments:**
- `name` — agent name to delete
- `confirm` — required `yes`

**Behavior:**
1. Deletes `agents/<name>.md`
2. Returns confirmation
