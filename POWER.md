---
name: "swamp"
displayName: "Swamp Automation"
description: "AI-native automation with typed models, versioned data, CEL queries, and workflow orchestration. Manage infrastructure, APIs, and services through observation-first patterns."
keywords: ["swamp", "model", "workflow", "automation", "infrastructure", "CEL", "extension", "typed data", "observation", "adopt"]
author: "webframp"
---

# Swamp Power

## Overview

Swamp is an AI-native automation CLI that replaces static declarations with observation-first patterns. Models observe live systems, store typed versioned data, and workflows orchestrate parallel execution.

**Key capabilities:**
- **Models** — Typed automation units with Zod schemas, methods, and versioned output
- **Workflows** — DAG-based orchestration with parallel jobs and CEL conditions
- **Data** — Immutable versioned snapshots queryable with CEL expressions
- **Extensions** — Community registry of model types for AWS, GCP, Azure, GitHub, and more

## Available Steering Files

- **model-operations** — Creating, editing, running methods, factory patterns
- **extension-development** — Building custom TypeScript model extensions
- **data-and-cel** — CEL query patterns, data lifecycle, latest/history
- **workflow-orchestration** — DAG design, parallel jobs, dependsOn, scheduling

## Onboarding

### Step 1: Verify swamp is installed

Run `swamp version` to confirm the CLI is available. If not installed, see https://github.com/systeminit/swamp for installation.

### Step 2: Check repository status

Run `swamp model search` to see if this workspace is a swamp repository. If no results, the workspace may need initialization with `swamp init`.

### Step 3: Explore available types

Run `swamp model type search` to see installed model types. Use `swamp extension search` to find community extensions.

## Rules

1. **Search before you build.** Search community extensions with `swamp extension search` — prefer `@swamp/*` official extensions. Only create custom extensions as a last resort.
2. **Extend, don't be clever.** When a model covers the domain but lacks the method you need, extend it. Don't bypass with shell scripts.
3. **Use the data model.** Reference existing data with CEL expressions. Don't re-fetch what's already stored.
4. **CEL expressions everywhere.** Wire models together with `data.latest("<name>", "<dataName>").attributes.<field>`.
5. **Verify before destructive operations.** Always `model_get` and verify resource IDs before delete/destroy methods.
6. **Prefer fan-out methods over loops.** A single method that handles multiple targets internally avoids per-model lock contention.

## When to Load Steering Files

- Creating or editing models → `model-operations.md`
- Building custom TypeScript extensions → `extension-development.md`
- Querying data or working with CEL → `data-and-cel.md`
- Creating or running workflows → `workflow-orchestration.md`
