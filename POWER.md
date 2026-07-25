---
name: "swamp"
displayName: "Swamp Automation"
description: "AI-native automation with typed models, versioned data, CEL queries, and workflow orchestration. Manage infrastructure, APIs, and services through observation-first patterns."
keywords: ["swamp", "model", "workflow", "automation", "infrastructure", "CEL", "extension", "typed data", "observation", "adopt", "swamp model", "swamp workflow", "swamp data", "swamp vault", "swamp extension", "swamp report", "swamp serve"]
author: "webframp"
---

# Swamp Power

## Overview

Swamp is an AI-native automation CLI that replaces static declarations with
observation-first patterns. Models observe live systems, store typed versioned
data, and workflows orchestrate parallel execution.

This power provides keyword-triggered discoverability for swamp within Kiro. All
operational guidance is provided by the **swamp skill** — activate it
immediately after this power loads.

## CRITICAL: Activate the Swamp Skill

When this power activates, you MUST also activate the `swamp` skill using
`disclose_context` with name `"swamp"`. The skill contains all authoritative
operational guidance: commands, rules, guardrails, and deep reference material
maintained in sync with the swamp CLI.

Do not answer swamp questions from this file alone. This power exists for
discoverability; the skill is the source of truth.

## Key Capabilities

- **Models** — Typed automation units with Zod schemas, methods, and versioned output
- **Workflows** — DAG-based orchestration with parallel jobs and CEL conditions
- **Data** — Immutable versioned snapshots queryable with CEL expressions
- **Extensions** — Community registry of model types for AWS, GCP, Azure, GitHub, and more
- **Vaults** — Secret storage referenced by models at runtime
- **Reports** — Post-execution analysis of method and workflow output
- **Serve** — Expose repos over the network with auth and grant-based access control

## Onboarding

### Step 1: Verify swamp is installed

Run `swamp version` to confirm the CLI is available. If not installed, see
https://github.com/systeminit/swamp for installation.

### Step 2: Check repository status

Run `swamp model search` to see if this workspace is a swamp repository. If no
results, the workspace may need initialization with `swamp repo init`.

### Step 3: Explore available types

Run `swamp model type search` to see installed model types. Use
`swamp extension search` to find community extensions.

## Rules

1. **Activate the skill first.** Always load the swamp skill before answering
   any swamp question. The skill's routing table determines which guide to load.
2. **Use the CLI, not workarounds.** Interact with swamp through its CLI
   commands. Don't grep `.swamp/` files, don't bypass model methods with raw
   tools like `aws` or `curl` when a model type covers the operation.
3. **Search before you build.** Check community extensions with
   `swamp extension search` before creating custom ones. Prefer `@swamp/*`
   official extensions.
4. **Verify before destructive operations.** Inspect with
   `swamp model get <name> --json` and confirm resource IDs before running
   delete, stop, or destroy methods.
