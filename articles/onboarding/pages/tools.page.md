---
name: tools
type: page
about: Install commands and directory conventions.
---

# Tools Setup

## Claude Code

```bash
brew install anthropic/claude-code/claude
claude auth
```

## tmux

```bash
brew install tmux
```

## oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Git

```bash
xcode-select --install
```

## Directory Convention

Keep repos in `~/src/`:

```bash
mkdir -p ~/src
git clone https://github.com/user/repo.git ~/src/repo
```
