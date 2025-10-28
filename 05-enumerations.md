# 🔢 Enumerations

- Fields might only accept a limited set of values.
- The API **may** expose enum objects for infrequently changing sets of values.
- Enum values **must** be in UPPER_SNAKE_CASE.
- First value of enum **should** be the name of the enum followed by `_UNSPECIFIED`.
- Enums with a single use case **should** be declared immediately before use.
- Eums with multiple use cases **should** be declared at the package level.
- Enums **should** document whether they are frozen or expected to change.

### When to use enums

- Enums are more accessible than strings, but add overhead when they change.
- Enums **should** receive new values infrequently.

### Alternatives

- If the enum changes frequently, the API **should** use a string.
  - The API **should** document the allowed values.
  - The string field **should** use `kebab-case`.
- Enums **should not** be used if there is a better standard representation.
- Boolean fields **may** be used if no further flexibility is needed.
  - The default value **must** be `false`.
