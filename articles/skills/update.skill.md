---
name: update
type: skill
about: Updates frontmatter or content. Patch or replace.
---

# Update

## Arguments

- `path` — file path, e.g. `articles/skills/read.skill.md`
- `mode` — `patch` or `replace`

## Patch Mode

Pass fields to update directly:

```
/update articles/skills/read.skill.md patch about="New about."
```

Fields: `about` (frontmatter), `body` (Markdown body).

## Replace Mode

```
/update articles/skills/read.skill.md replace content="<full file>"
```

Overwrites the entire file.

## Notes

- Path traversal (`..`) is rejected
- File must exist
