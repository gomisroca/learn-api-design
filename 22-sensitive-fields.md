# Sensitive Fields

- If sensitive data is required for the resource to exist, the data **should** be accepted as input-only field.
- If sensitive data is optional, an output-only boolean field **should** be used to indicate whether the data is present. It should have a postfix of `_set`.
- If we need to identify the data without revealing it, a field of same type with prefix `obfuscated_` **may** be used to provide context.
