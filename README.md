# Ghostline

Claude Code skills for the [Ghostline documentation standard](https://signalshell.com/ghostline).

## Skills

Three slash commands for working with Ghostline docs in any project:

| Command | Description |
|---|---|
| `/ghostline-init` | Initialize Ghostline docs for a project from scratch |
| `/ghostline-sync` | Update docs to reflect recent code changes |
| `/ghostline-check` | Check whether docs are consistent with the current code |

## Install

Copy the skills into your project's `.claude/commands/` folder:

```sh
mkdir -p .claude/commands
curl -o .claude/commands/ghostline-init.md https://raw.githubusercontent.com/signalshell/ghostline/main/.claude/commands/ghostline-init.md
curl -o .claude/commands/ghostline-sync.md https://raw.githubusercontent.com/signalshell/ghostline/main/.claude/commands/ghostline-sync.md
curl -o .claude/commands/ghostline-check.md https://raw.githubusercontent.com/signalshell/ghostline/main/.claude/commands/ghostline-check.md
```

Or clone and copy manually.

## What is Ghostline?

Ghostline is a documentation standard for agent-managed codebases. Three markdown layers (System, Container, Component) based on the C4 model. Agents maintain the docs as a side effect of development. Humans read at whatever altitude they need.

Full spec: [signalshell.com/ghostline](https://signalshell.com/ghostline)
