---
name: overview
type: page
about: What articles are, why they exist, and the problems they solve.
---

# Overview

Articles organizes knowledge into three types:

- **skills** — do this (directives)
- **pages** — when to do this and in what order (workflow guidance)
- **articles** — entry points that coordinate skills and pages for a topic

## Access Pattern

```
manifest.json → <name>.article.md → skills/ or pages/
```

Skills and pages are never accessed directly.

## Reference Files

Each article can have a `reference/` directory. Reference files are private to each article. Link from skills/pages as `../reference/<file>`.
