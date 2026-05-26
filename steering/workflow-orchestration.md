# Workflow Orchestration

## Design

Workflows are YAML DAGs with parallel jobs. Jobs contain steps that execute model methods. Use `dependsOn` to express ordering constraints — everything else runs concurrently.

## Creating Workflows

Use `workflow_search` to see existing workflows. Validate with `workflow_validate` before running.

## Execution

`workflow_run` executes the full DAG. Jobs without dependencies start immediately in parallel. Steps within a job run sequentially.

## Patterns

- **Fan-out**: A single job step that calls a fan-out method on a model, producing multiple outputs
- **Conditional execution**: Use CEL expressions in `condition` fields to skip steps based on prior output
- **Scheduling**: Workflows support cron-style scheduling via `swamp serve --webhook`

## Rules

- Prefer concurrent agents sharing typed state over sequential pipeline stages
- Each job should represent a logical unit of work, not a single API call
- Use `dependsOn` only when data flows between jobs — don't serialize unnecessarily
