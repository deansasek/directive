---
name: validate
type: skill
about: Validates a commit message against conventional commits.
---

# Validate

Checks if a commit message conforms to conventional commits.

**Arguments:**
- `message` — the commit message to validate

**Regex:** `^(feat|fix|chore|docs|style|refactor|perf|test|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$`

**Common failures:**
- Summary not lowercase
- Missing `: `
- Header over 72 chars
