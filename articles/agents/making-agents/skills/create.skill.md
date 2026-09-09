---
name: create
type: skill
about: Creates a new agent .md file in agents/.
---

# Create Agent

Scaffolds a new agent file in `agents/`.

**Arguments:**
- `name` — agent name (lowercase, hyphens)
- `description` — when to use this agent
- `tools` — comma-separated tool list
- `color` — color for agent (blue, green, orange, cyan, yellow, red, purple)
- `background` — optional, set to `true` for background agents

**Behavior:**
1. Creates `agents/<name>.md` with frontmatter and body
2. Returns confirmation

**Example:**
```
/making-agents:create name=reviewer description="Reviews code for bugs" tools=Read,Grep,Bash color=yellow
```
