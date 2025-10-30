# Methods: Update

- APIs **should** provide an `Update` method for resources.
- RPC name **must** begin with the word `Update` followed by the singular resource name. E.g. `UpdateUser`.
- The request msg **must** match the RPC name, with a `Request` suffix.
- The response msg **must** be the resource itself.
- The HTTP Verb **must** be `PATCH`.
- The resource's `name`field **should** map to the URI path.

### Request Message

- The request msg **must** contain a field for the resource.
  - The field **must** map to the PATCH body.
  - The field `name` **must** be included.
- If partial updates are supported, the request msg **must** contain a field for the partial update mask.
- The request msg **must not** contain any other fields.

### Side effects

- Update methods **should not** trigger side effects.
- Side effects **should** be triggered by custom methods.
