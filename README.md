# Articles

A system for organizing knowledge into articles, skills, and pages.

## Install

```bash
cp -r articles ~/.claude/articles
```

Then add to `~/.claude/CLAUDE.md`:

```
See `.claude/articles/manifest.json` to discover articles.
```

## Structure

```
articles/
  manifest.json
  <name>/
    <name>.article.md
    skills/
    pages/
    reference/
```

## Articles Article

The `articles` article explains the system and contains 7 core skills: list, read, peek, create, update, delete, regenerate.
