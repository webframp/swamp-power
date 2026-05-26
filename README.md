# swamp-power

A [Kiro Power](https://kiro.dev/docs/powers/) for [swamp](https://github.com/systeminit/swamp) — AI-native automation with typed models, versioned data, and workflow orchestration.

## Installation

In Kiro IDE: **Powers panel → Add power from GitHub** → `webframp/swamp-power`

## What's Included

- **POWER.md** — Activation keywords, onboarding steps, and rules
- **mcp.json** — MCP server configuration (spawns [swamp-mcp-server](https://github.com/webframp/swamp-mcp-server))
- **steering/** — Workflow-specific guidance loaded on demand:
  - `model-operations.md` — Model CRUD, methods, factory patterns
  - `extension-development.md` — Building custom TypeScript extensions
  - `data-and-cel.md` — CEL queries and data lifecycle
  - `workflow-orchestration.md` — DAG design and parallel execution

## Requirements

- [swamp](https://github.com/systeminit/swamp) CLI installed
- [Deno](https://deno.land/) >= 2.0 (for the MCP server)

## How It Works

When you mention "swamp", "model", "workflow", or related keywords in Kiro, this power activates — loading the MCP server tools and relevant steering into context. When you move to a different task, it deactivates.

## License

MIT
