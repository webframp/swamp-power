# swamp-power

A [Kiro Power](https://kiro.dev/docs/powers/) for [swamp](https://github.com/systeminit/swamp) — AI-native automation with typed models, versioned data, and workflow orchestration.

## What This Does

This is a **Knowledge Base Power** that provides keyword-triggered
discoverability for swamp within Kiro. When you mention "swamp", "model",
"workflow", or related keywords, Kiro activates this power and loads the
`swamp` skill for authoritative operational guidance.

The power is intentionally thin. It exists to bridge Kiro's power activation
system to the swamp skill, which is maintained in sync with the swamp CLI by
the upstream developers.

## Installation

In Kiro IDE: **Powers panel → Add power from GitHub** → `webframp/swamp-power`

## What's Included

- **POWER.md** — Activation keywords, onboarding steps, and a directive to load the swamp skill

## Requirements

- [swamp](https://github.com/systeminit/swamp) CLI installed
- The `swamp` skill installed at `~/.kiro/skills/swamp/`

## How It Works

1. You mention a swamp-related keyword in Kiro
2. This power activates, loading POWER.md into context
3. POWER.md instructs the agent to activate the `swamp` skill via `disclose_context`
4. The skill provides all operational guidance (commands, rules, guardrails, deep references)

The skill is the source of truth. This power is a discoverability layer.

## License

MIT
