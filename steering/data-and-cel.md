# Data and CEL Queries

## Data Lifecycle

Every method execution produces immutable, versioned output stored in the model's data catalog. Use `model_output` to retrieve the latest snapshot.

## CEL Expressions

Wire models together with CEL. The canonical pattern:

```
data.latest("<modelName>", "<dataName>").attributes.<field>
```

Use `data_query` to run ad-hoc CEL queries across all versioned data in the repository.

## Common Patterns

- Filter resources: `data.latest("ec2", "instances").attributes.instances.filter(i, i.state == "running")`
- Cross-model references: use one model's output as input to another via CEL in workflow steps
- Historical queries: `data.history("<name>")` for version comparisons

## Rules

- Never re-fetch data that already exists in the data model
- Prefer `data.latest()` over the deprecated `model.<name>.resource.<spec>.<instance>.attributes.<field>` pattern
