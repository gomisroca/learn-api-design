# Batch Methods: Delete

- APIs **may** support Batch Delete
- The RPC name **must** begin with `BatchDelete`. The remainder **should** be the plural of the resource name.
- The request **must** match the RPC name, with Request suffix.
- The HTTP method **must** be `POST`
- The HTTP URI **must** end with `:batchDelete`
- The URI path **should** represent the collection for the resource.

### Atomic vs. Partial Success

- The batch delete **may** support atomic or partial success.
- Synchronous batch delete **must** be atomic.
- Asynchronous batch delete **may** be atomic or partial success.

### Request Message

- A parent field **should** be included.
  - **Should** be required if only 1 parent is allowed.
  - **Should** identify the parent resource type.
- **Must** include a repeated field with the names of the resources to delete.
  - It **should** be named `names`.
  - It **should** be required.
- The req msg **must not** contain any other required fields.

### Response Message (soft-delete only)

- **Must** include one field corresponding to the soft-deleted resource.
