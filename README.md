# Ultralite

An engineering toolkit for Claude Code agents — agents, articles, and conventions for consistent engineering.

## Install

```bash
git clone https://github.com/deansasek/ultralite.git
claude --plugin-dir ./ultralite
```

Or auto-load:

```bash
cp -r ultralite ~/.claude/skills/ultralite
```

## Agents

| Agent | Role |
|-------|------|
| `@project-manager` | Orchestrates tasks, delegates |
| `@researcher` | Explores codebases, surfaces findings |
| `@engineer` | Implements, scaffolds, fixes |
| `@linter` | Runs linters and formatters |
| `@query` | SQL queries and data access |

## Articles

See `articles/manifest.json` for all articles, or read `articles/meta/articles/articles.article.md`.

### software-engineering
onboarding, github, kotlin, restful-apis, core-design-principles, testing

### agents
making-agents

### meta
articles
