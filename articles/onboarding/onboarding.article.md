---
name: onboarding
type: article
about: Engineering environment setup — tools, directory conventions, and environment checks.
---

# Onboarding

Get your engineering environment set up.

## Tools

- **Claude Code** — `brew install anthropic/claude-code/claude`
- **tmux** — `brew install tmux`
- **oh-my-zsh** — `sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
- **Git** — `xcode-select --install`

## Directory Convention

Clone repos to `~/src/` to keep them organized:

```bash
mkdir -p ~/src
git clone https://github.com/user/repo.git ~/src/repo
```

## Skills

- **init** — create `~/src/` if missing
- **validate** — check if all tools are installed and `~/src/` exists
