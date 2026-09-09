---
name: update
type: skill
about: Updates frontmatter fields or replaces the full content of a file.
---

# Update

**Arguments:**
- `path` — path to the file relative to the repo root, e.g. `articles/github/skills/pr-validate.skill.md`
- `mode` — `patch` or `replace`

## Patch Mode

Updates specific fields without touching the rest of the file.

```
/update <path> patch about="New about text."
```

**Updatable fields:**
- `about` — updates the `about` frontmatter field
- `name` — updates the `name` frontmatter field (use with caution; may break references)
- `body` — replaces the Markdown body content (everything after the frontmatter block)

All other content is preserved.

## Replace Mode

Overwrites the entire file.

```
/update <path> replace content="<full file content>"
```

**Behavior:**
1. Validates path: no `..` allowed
2. For `patch`: reads file, merges specified fields, writes back
3. For `replace`: writes the provided content as the new file
4. Returns a summary of what changed

**Errors:**
- "path traversal not allowed" if `..` in path
- "file not found at <path>" if file doesn't exist
