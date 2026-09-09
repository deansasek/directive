---
name: ultralite
type: skill
about: Ultralite engineering toolkit — agents, articles, and conventions.
---

# Ultralite

An engineering toolkit for Claude Code agents.

## Agents

Located in `agents/`. Invoke as `/ultralite:<agent-name>`.

- `@project-manager` — orchestrates tasks
- `@researcher` — explores codebases
- `@engineer` — implements and fixes
- `@linter` — runs linters
- `@query` — data access

## Articles

Located in `articles/`. Index at `articles/manifest.json`.

Read an article: open `articles/<domain>/<name>/<name>.article.md`.

## Core Skills

Article-system skills live in `articles/meta/articles/skills/`. Read them to manage articles:

- `list` — list all articles from manifest
- `read` — read a file by path
- `peek` — read frontmatter only
- `create` — create article, skill, or page
- `update` — update frontmatter or content
- `delete` — delete article, skill, or page
- `regenerate` — regenerate manifest
