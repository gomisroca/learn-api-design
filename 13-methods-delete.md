# Methods: Delete

- APIs **should** provide a `Delete` method for resources.
- RPC name **must** begin with the word `Delete` followed by the singular resource name.
- The request msg **must** match the RPC name, with a `Request` suffix.
- The HTTP Verb **must** be `DELETE`.
- The resource's `name` field **should** map to the URI path.
- APIs **must** fail with a `FAILED_PRECONDITION` status code if child resources exist.
- Delete **should** succeed only if a resource was present and is now deleted. If the resource was not present, the API **must** fail with a `NOT_FOUND` status code.

### Request Message

- A `name` field **must** be included.
- The request msg **must not** contain any other fields.

### Long-running Delete

- If the resource takes a while to delete, the API **should** use a long-running operation.

### Cascading Delete

- If the API allows cascading deletes, it **should** provide a bool `force`, which opts into a cascading delete.
- The API **must** fail with a `FAILED_PRECONDITION` status code if the `force` field is set to `false` and the resource has children.

### Errors

- If the user does not have permission to delete the resource, the API **must** fail with a `PERMISSION_DENIED` status code.
- Permission **must** be checked before checking if the resource exists.
- If the user has permission to delete the resource, but the resource does not exist, the API **must** fail with a `NOT_FOUND` status code.
