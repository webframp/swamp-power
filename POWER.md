---
name: "swamp"
displayName: "Swamp Automation"
description: "Force-loads the global swamp skill so Kiro always has authoritative swamp CLI guidance without the operator repeating themselves."
keywords: ["swamp", "model", "workflow", "automation", "infrastructure", "CEL", "extension", "typed data", "observation", "adopt", "swamp model", "swamp workflow", "swamp data", "swamp vault", "swamp extension", "swamp report", "swamp serve"]
author: "webframp"
---

# Swamp Power

## What this power does

This power has exactly one job: when any swamp-related keyword appears, force
Kiro to load the global `swamp` skill at `~/.kiro/skills/swamp/`. That skill is
the single source of truth for every swamp operation — its routing table,
commands, guardrails, and deep reference guides are maintained in sync with the
swamp CLI.

The power carries no MCP server, no bundled steering, and no inlined command
reference. The surface is the **swamp skill plus the swamp CLI**, nothing else.

## CRITICAL: Activate the swamp skill

When this power activates, you MUST immediately activate the `swamp` skill using
`disclose_context` with name `"swamp"`. Do this before answering any swamp
question.

Do not answer swamp questions from this file. This file exists only to trigger
skill activation. All authoritative guidance — commands, rules, guardrails, and
reference material — lives in the skill.

## Requirement

The global `swamp` skill must be installed at `~/.kiro/skills/swamp/`. Without
it, this power has nothing to delegate to. If the skill is missing, tell the
operator to install it rather than improvising swamp guidance from memory.
