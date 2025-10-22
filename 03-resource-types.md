# 🦠 Resource Types

- The API **must** define a resource type for each resource in the format `{Service Name}/{Type}`.
- Service Name often matches the hostname (e.g. `pubsub.googleapis.com`).
- Type name **must** match the containing API type's name.
- Type name **must** be in PascalCase.
- Type name **must** be in singular form.

### Examples

- `pubsub.googleapis.com/Topic`
- `spanner.googleapis.com/Database`
