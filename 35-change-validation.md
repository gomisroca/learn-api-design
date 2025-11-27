# Change Validation

- APIs **may** provide an option to validate a request without executing it.
- The req msg **should** include a `validate_only` bool field.
- The API **must** perform permission checks and any other validation used in a 'live' request.
- If a 'live' request would fail, the `validate_only` request **must** fail too.
- A declarative-friendly resource **must** include a `validate_only` field on mutation methods.
