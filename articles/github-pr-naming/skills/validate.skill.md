---
name: validate
type: skill
about: Validates a PR title against the enterprise naming standard.
---

# Validate

Checks if a PR title conforms to the standard.

**Arguments:**
- `title` — the PR title to validate

**Behavior:**
1. Match against `^(\[[A-Z0-9]+-[0-9]+\] )?(feat|fix|chore|refactor|perf|test|docs|style|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$`
2. Return PASS or FAIL with reason

**Common failures:**
- Ticket ID not uppercase: `[api-4029]` → `[API-4029]`
- Description starts uppercase: `Add user avatar` → `add user avatar`
- Missing colon: `fix(ui) resolve` → `fix(ui): resolve`
- WIP prefix not allowed
