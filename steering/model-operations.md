# Model Operations

## Creating Models

Use `model_type_search` to find the right type, then `model_type_describe` to understand its schema and available methods before creating.

Models follow the factory pattern: one model manages a collection of resources. Methods operate on targets by argument rather than one model per resource.

## Running Methods

Use `model_method_run` with the model name, method name, and any required arguments. Check `model_type_describe` first to see parameter requirements.

Fan-out methods handle multiple targets in a single invocation. Prefer these over calling the same method repeatedly — multiple parallel calls against the same model contend on the per-model lock.

## Validating

Always `model_validate` after editing a model definition. This catches schema errors before execution.

## Output and State

`model_output` returns the latest versioned data snapshot from a model's most recent method execution. This data is immutable and queryable with CEL.
