# Server-Modified Values and Defaults

- Services often provide default values for fields, and normalize user input before returning it.

### Single Owner Fields

- Fields **must** have a single owner.
- Server owned fields **must** be marked as `OUTPUT_ONLY`.
- All other fields **must** be considered client owned.
- The server **must** respect the value of client-owned fields.

### Effective Values

- Sometimes, the service will generate a value for a field if the client does not provide one. These are called effective values.
- An attribute with an effective value **must** be expressed as two fields:
  - a mutable field optionally set by the client, **must not** be modified by the service.
  - an `OUTPUT_ONLY` field that sets the effective value decided by the service.
- Effective values **must** be prefixed with `effective_`.

### User-Specified Fields

- The value in response from the service **must** be the same as provided by the create/update request.
