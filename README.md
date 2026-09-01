# swamp-power

A [Kiro Power](https://kiro.dev/docs/powers/) for [swamp](https://github.com/systeminit/swamp) — AI-native automation with typed models, versioned data, and workflow orchestration.

## What this does

This power exists to force Kiro to load the global `swamp` skill whenever a
swamp-related keyword comes up, so the operator never has to keep pointing the
agent at the skill by hand.

It is intentionally thin. It carries **no MCP server** and **no bundled
steering**. The entire operational surface is the `swamp` skill (installed at
`~/.kiro/skills/swamp/`) plus the `swamp` CLI. The power is only a
discoverability trigger; the skill is the source of truth and is maintained in
sync with the CLI upstream.

## Format

This power follows the [Agent Plugins](https://agent-plugins.org/) specification.

- **`plugin.json`** — the manifest Kiro reads: `name`, `version`, `description`,
  `author`, and the `keywords` that trigger activation.
- **`POWER.md`** — retained for backward compatibility with the legacy power
  format (Kiro still supports it). Its body is a directive to activate the
  `swamp` skill via `disclose_context`.

There is deliberately no `skills/`, no `mcp.json`, and no `dev.kiro/steering/`.

## Requirements

- The [swamp](https://github.com/systeminit/swamp) CLI installed.
- The `swamp` skill installed at `~/.kiro/skills/swamp/`.

## Installation

In Kiro IDE: **Powers panel → Add Custom Power → Import power from GitHub** →
`webframp/swamp-power`.

Or import from a local folder for development: **Add Custom Power → Import power
from a folder** → select this directory.

## How it works

1. You mention a swamp-related keyword in Kiro.
2. Kiro evaluates the power's `keywords` and activates it.
3. The power instructs the agent to activate the `swamp` skill via
   `disclose_context`.
4. The skill provides all operational guidance — routing table, commands, rules,
   guardrails, and deep references.

## License

MIT
