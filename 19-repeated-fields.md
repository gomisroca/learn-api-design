# Repeated Fields

- Repeated fields **must** use a plural name.
- Repeated fields **should** have an enforced upper bound, usually 100 elements.
- Repeated fields **must not** represent the body of another resource inline.

### Scalars and Messages

- Repeated fields **should** use a scalar type (e.g. string) if possible.
- If additional data will be needed, the field **should** use a message type.

### Update Strategies

- A resource **may** use standard Update method, or custom Add/Remove methods.
- The data added/removed **should** be a primitive.
- The RPC name **must** begin with `Add` or `Remove`.
  - The remainder of the name **should** be the singular form of the field name.
- The request message **must** match the resource name, with a `Request` suffix.
- The response message **should** be the resource itself.
- The HTTP method **must** be `POST`.
- The HTTP URI **must** end with `:add*` or `:remove*`, where `*` is the snake-case singular form of the field name.
- If the data added already exists, the method **must** error with `ALREADY_EXISTS`.
- If the data removed does not exist, the method **must** error with `NOT_FOUND`.

### Request Message

- A resource field **must** be included.
  - It **should** be the name of the resource.
  - It **should** identify the resource type it references.
- A field for the value being added/removed **must** be included.
  - It **should** be the singular name of the field.
- The request message **must not** contain any other fields.
