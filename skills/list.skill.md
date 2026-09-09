---
name: list
type: skill
about: Lists all articles from the manifest. Auto-regenerates the manifest if it is missing.
---

# List

Reads `manifest.json` and returns all articles as a formatted list.

**Behavior:**
- Reads `manifest.json`
- If the file does not exist, runs `regenerate` automatically, then re-reads
- Returns each article's `name`, `type`, and `about`

**Output format:**
```
- <name> (<type>): <about>
```
