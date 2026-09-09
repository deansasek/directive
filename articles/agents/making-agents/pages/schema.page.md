---
name: schema
type: page
about: Agent frontmatter schema and fields.
---

# Agent Schema

Agents are `.md` files in `agents/` with YAML frontmatter.

```markdown
---
name: <agent-name>
description: <when to use this agent>
tools: Read, Write, Edit, Glob, Grep, Bash
permissionMode: acceptEdits
color: <color>
effort: <low|medium|high>
background: <true|false>
---

<system prompt>
```

## Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Lowercase, hyphens only |
| `description` | Yes | When to delegate to this agent |
| `tools` | No | Comma-separated tool allowlist |
| `permissionMode` | No | `acceptEdits` auto-accepts file edits |
| `color` | No | `blue`, `green`, `orange`, `cyan`, `yellow`, `red`, `purple` |
| `effort` | No | `low`, `medium`, `high` |
| `background` | No | `true` for fire-and-forget workers |
| `model` | No | `sonnet`, `opus`, `haiku` |
