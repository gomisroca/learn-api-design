# Field Names

- Field names **should** be in American English.
- Field names **should** clearly and concisely describe the field.
- Field names **should** avoid unnecessary words.

### Case

- Field names **must** use `lower_snake_case`.
- Each word in the name **must not** start with a number.
- Each word in the name **must not** contain leading or trailing underscores.

### Uniformity

- APIs **should** use the same name for the same concept wherever possible.

### Repeated Fields

- Repeated fields **must** use the proper plural form. E.g. `books` or `authors`.

### Prepositions

- Field names **should not** contain prepositions.

### Abbreviations

- Field names **should** well-known abbreviations.

### Adjectives

- Fields names with adjectives **should** place the adjective before the noun.

### Verbs

- Field names **must not** reflect an intent or action.
- Field names **must not** be verbs.

### Booleans

- Boolean fields **should** omit the `is_` prefix. E.g. `disabled`, not `is_disabled`.
