---
name: commit-suggest
type: skill
about: Suggests a conventional commit message.
---

# Commit Suggest

**Args:** `description`, `type`, `scope`

**Output:** `type(scope): imperative summary`

**Example:** `commit-suggest "fix auth session drop on 503" type=fix scope=auth` → `fix(auth): prevent session drop on 503`
