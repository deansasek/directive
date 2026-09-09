---
name: pr-validate
type: skill
about: Validates a PR title against the conventional format.
---

# PR Validate

Validates a PR title against the conventional format: `[TICKET] type(scope): imperative description`

**Arguments:**
- `title` — the PR title to validate

**Regex:** `^(\[[A-Z0-9]+-[0-9]+\] )?(feat|fix|chore|refactor|perf|test|docs|style|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$`

**Output:** `valid` or `invalid` with the reason if invalid.
