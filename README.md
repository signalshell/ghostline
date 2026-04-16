# Ghostline

Claude Code skills for the [Ghostline documentation standard](https://signalshell.com/ghostline).

## Skills

Three slash commands for working with Ghostline docs in any project:

| Command | Description |
|---|---|
| `/ghostline:ghostline-init` | Initialize Ghostline docs for a project from scratch |
| `/ghostline:ghostline-sync` | Update docs to reflect recent code changes |
| `/ghostline:ghostline-check` | Check whether docs are consistent with the current code |

## Install

```sh
claude plugin install github:signalshell/ghostline
```

## What is Ghostline?

C4 is the best architecture documentation standard for humans, but it is not good for agents. Agents work much better with text than with diagrams.

Ghostline takes the C4 structure (System Context, Container, Component) and replaces every diagram with prose, lists, and tables. Agents maintain the docs as a side effect of development. Humans read at whatever altitude they need.

Full spec: [signalshell.com/ghostline](https://signalshell.com/ghostline)
