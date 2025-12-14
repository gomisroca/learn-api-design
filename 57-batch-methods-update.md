# Batch Methods: Update

- APIs **may** support Batch Update
- The RPC name **must** begin with `BatchUpdate`. The remainder **should** be the plural of the resource name.
- The request and response messages **must** match the RPC name, with Request and Response suffixes.
- The HTTP method **must** be `POST`
- The HTTP URI **must** end with `:batchUpdate`
- The URI path **should** represent the collection for the resource.

### Atomic vs. Partial Success

- The batch update **may** support atomic or partial success.
- Synchronous batch update **must** be atomic.
- Asynchronous batch update **may** be atomic or partial success.

### Request Message

- A parent field **should** be included.
  - **Should** be required if only 1 parent is allowed.
  - **Should** identify the parent resource type.
- **Must** include a repeated field with the names of the resources to update.
  - It **should** be named `requests`.
  - It **should** be required.
- The req msg **must not** contain any other required fields.

### Response Message

- **Must** include a repeated field with the updated resources.
