---
name: commit-suggest
type: skill
about: Suggests a commit message given a change description.
---

# Commit Suggest

Suggests a commit message in conventional format: `<type>(<scope>): <summary>`

**Arguments:**
- `description` — brief description of the change (what and why, not how)
- `type` — optional type override (feat, fix, refactor, etc.)
- `scope` — optional scope (e.g., auth, api, ui)

**Output:** A valid commit message suggestion.
