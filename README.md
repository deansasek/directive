# Articles

A system for Claude Code agents to organize skills, documentation, and knowledge into articles.

## What Articles Is

Articles is a file-based knowledge system for AI agents. It solves:
- Token efficiency — load only what you need
- Selective loading — scan a manifest, load only relevant skills/pages
- Composition without duplication — articles coordinate, skills execute

## Install for Claude Code

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
  manifest.json        # Auto-generated index of all articles
  <name>/
    <name>.article.md  # Entry point — lists skills and pages
    skills/
    pages/
    reference/         # Files skills/pages reference
```

## How It Works

1. Read `manifest.json` to see all available articles
2. Open an article's `<name>.article.md` to see its skills and pages
3. Use the skills (list, read, peek, create, update, delete, regenerate) to navigate and manage

## Articles Article

The `articles` article is the meta-article — it explains the system and contains its own documentation. Read it to understand how articles work.
