# Ghostline

Claude Code skills for the [Ghostline documentation standard](https://signalshell.com/ghostline).

## Skills

Four slash commands for working with Ghostline docs in any project:

| Command | Description |
|---|---|
| `/ghostline:init` | Initialize Ghostline docs for a project from scratch |
| `/ghostline:sync` | Code changed — update docs to match |
| `/ghostline:implement` | Docs changed — update code to match |
| `/ghostline:check` | Find drift and determine which side needs updating |

`sync` and `implement` are two directions of the same workflow. Use `check` when you are not sure which side has drifted.

## Install

```sh
claude plugin install github:signalshell/ghostline
```

## What is Ghostline?

C4 is the best architecture documentation standard for humans, but it is not good for agents. Agents work much better with text than with diagrams.

Ghostline takes the C4 structure (System Context, Container, Component) and replaces every diagram with prose, lists, and tables. Agents can read the structure selectively. Humans can read at whatever altitude they need. Either side can write — the format works in both directions.

Full spec: [signalshell.com/ghostline](https://signalshell.com/ghostline)
