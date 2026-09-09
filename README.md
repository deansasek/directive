# Directive

An engineering toolkit for Claude Code agents — agents, articles, and conventions for consistent engineering.

## Install

```bash
git clone https://github.com/deansasek/directive.git
claude --plugin-dir ./directive
```

Or auto-load:

```bash
cp -r directive ~/.claude/skills/directive
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

See `articles/manifest.json` for all articles.

**Core:** articles, onboarding
**Conventions:** github, core-design-principles, testing
**Languages:** kotlin
