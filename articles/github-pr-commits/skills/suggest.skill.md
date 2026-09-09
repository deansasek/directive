---
name: suggest
type: skill
about: Suggests a conventional commit message.
---

# Suggest

**Arguments:**
- `description` — what changed
- `type` — type hint (e.g., `feat`, `fix`)
- `scope` — component (e.g., `auth`, `billing`)

**Output:** `type(scope): imperative summary`

**Example:** `suggest "fix auth session drop on 503" type=fix scope=auth` → `fix(auth): prevent session drop on 503`
