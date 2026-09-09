---
name: anatomy
type: page
about: File types, frontmatter, directory structure, and naming conventions.
---

# Anatomy

## File Types

### `<name>.article.md`
The article entry point. Lives in `articles/`. Contains frontmatter and lists its skills and pages.

### `<name>.skill.md`
A skill — step-by-step directives. Lives in `skills/` at the repo root.

### `<name>.page.md`
A page — workflow guidance. Lives in `pages/` at the repo root.

## Frontmatter

```yaml
---
name: <identifier>
type: <article | skill | page>
about: <2-3 sentence summary>
---
```

For articles, `name` must match the filename without `.article.md`.

## Directory Structure

```
<plugin>/
  manifest.json
  skills/
  pages/
  articles/
    <name>/
      <name>.article.md
      reference/
```

## Naming

- kebab-case: `timeline`, `create-milestone`
- article file matches its directory: `articles/timeline/timeline.article.md`

## Reference Files

Reference files live in `articles/<name>/reference/` and are private to each article.

From skills/pages, link as: `../articles/<name>/reference/<filename>`
From the article file, link as: `articles/<name>/reference/<filename>`

Use for: diagrams, code samples, pseudocode, any file a skill or page needs to reference.
