---
name: commit-validate
type: skill
about: Validates a commit message against conventional commits.
---

# Commit Validate

**Regex:** `^(feat|fix|chore|docs|style|refactor|perf|test|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$`

**Rules:**
- Summary lowercase, imperative, under 72 chars
- No period at end
