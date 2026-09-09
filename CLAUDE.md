# Directive

An engineering toolkit for Claude Code agents.

## Agents

Invoke as `/directive:<agent-name>`.

- `@project-manager` — orchestrates tasks, delegates to researcher and engineer
- `@researcher` — explores codebases, surfaces findings
- `@engineer` — implements, scaffolds, refactors, fixes
- `@linter` — runs linters and formatters
- `@query` — SQL queries and data access

## Articles

Located in `articles/`. Index at `articles/manifest.json`.

To read an article: open `articles/<name>/<name>.article.md`.

## Article Skills

Manage articles via the article-system skills (read `articles/articles/skills/<skill>.skill.md` for details):

- `list` — list all articles from manifest
- `read` — read a file by path
- `peek` — read frontmatter only
- `create` — create article, skill, or page
- `update` — update frontmatter or content
- `delete` — delete article, skill, or page
- `regenerate` — regenerate manifest

## Article Index

7 articles: `articles`, `core-design-principles`, `github`, `kotlin`, `making-agents`, `onboarding`, `testing`
