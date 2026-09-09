---
name: pr-validate
type: skill
about: Validates a PR title against the naming standard.
---

# PR Validate

**Regex:** `^(\[[A-Z0-9]+-[0-9]+\] )?(feat|fix|chore|refactor|perf|test|docs|style|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$`

**Common failures:**
- Ticket ID not uppercase: `[api-1]` → `[API-1]`
- Description starts uppercase
- Missing `: `
- WIP prefix not allowed
