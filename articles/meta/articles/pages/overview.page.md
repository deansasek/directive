---
name: overview
type: page
about: What articles are, the three types, and the core concept.
---

# Overview

Articles organizes knowledge into three types:

- **skills** — do this (directives)
- **pages** — when to do this, in what order (workflow guidance)
- **articles** — entry points that coordinate skills and pages for a topic

Articles are never accessed directly. The path is always:

```
manifest.json → <name>.article.md → skills/ or pages/
```

Articles can have a `reference/` directory for files that skills/pages need to reference: diagrams, code samples, pseudocode. Reference files are private to each article.
