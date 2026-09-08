---
name: regenerate
type: skill
about: Scans all .article.md files and regenerates manifest.json.
---

# Regenerate

Scans `.claude/articles/` recursively for all `.article.md` files, extracts frontmatter, writes `manifest.json`.

Skips files with malformed frontmatter or duplicate names. Run after creating or deleting articles.
