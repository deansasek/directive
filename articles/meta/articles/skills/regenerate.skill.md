---
name: regenerate
type: skill
about: Scans all .article.md files and regenerates manifest.json with their frontmatter.
---

# Regenerate

Scans for all `.article.md` files under `articles/` and writes a fresh `manifest.json` inside `articles/`.

**Behavior:**
1. Recursively finds all files matching `*.article.md` under `articles/`
2. For each file:
   - Derives `name` from the filename: `timeline.article.md` → `name: timeline`
   - Extracts `type`, `about`, and `domain` from the YAML frontmatter
3. Validates entries:
   - Malformed frontmatter: skipped, warning returned
   - Duplicate `name`: skipped, warning returned
4. Writes `manifest.json` with all valid entries
5. Returns a summary: number of articles found, any skipped files with reasons

**Manifest format:**
```json
{"articles":[{"name":"<name>","domain":"<domain>","type":"article","about":"<about>"},...]}
```

**Notes:**
- Run this after creating or deleting articles
- The `list` skill auto-runs this if `manifest.json` is missing
- Skipped files do not block regeneration
