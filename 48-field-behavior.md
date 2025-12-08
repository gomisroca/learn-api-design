# Field Behavior Documentation

- APIs **must** at mininum use one of REQUIRED, OPTIONAL or OUTPUT_ONLY.

### Vocabulary

- IDENTIFIER: **must** be attached to the name field and not to any other field.
- IMMUTABLE: the service **should** error with INVALID_ARGUMENT if the field is mutated.
- INPUT_ONLY: only fields within resource messages **should** be described as input only.
- OPTIONAL: a field **may** be described as optional on a request message.
- OUTPUT_ONLY: on update requests, services **must** ignore output only fields. They **may** be set to empty values.
- REQUIRED: the field **must** be present. When creating, a value **must** be provided. When updating, it **may** be omitted.
- UNORDERED_LIST: repeated, unordered list. It **may** be ordered, or not.
