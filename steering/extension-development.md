# Extension Development

## When to Build

Only create a custom extension when:
1. `extension_search` returns no matching community extension
2. No installed type covers the domain (`model_type_search`)
3. An existing type can't be extended with `export const extension`

## Structure

Extensions are TypeScript files with Zod schemas. They define:
- `spec` — Input schema (what the user configures)
- `output` — Output schema (what methods produce)
- `methods` — Named functions that observe/act on external systems

## Key Patterns

- Pin npm dependencies with explicit versions: `npm:package@1.2.3`
- Swamp's bundler inlines all npm packages except zod
- Use `export const extension` to add methods to existing types
- One method, one purpose — don't build multi-step orchestration into a single method

## Testing

Validate extensions with `model_validate` after creating a model that uses the type. Run a method with `model_method_run` to verify end-to-end.
