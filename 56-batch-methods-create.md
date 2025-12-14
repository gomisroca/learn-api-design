# Batch Methods: Create

- APIs **may** support Batch Create
- The RPC name **must** begin with `BatchCreate`. The remainder **should** be the plural of the resource name.
- The request and response messages **must** match the RPC name, with Request and Response suffixes.
- The HTTP method **must** be `POST`
- The HTTP URI **must** end with `:batchCreate`
- The URI path **should** represent the collection for the resource.

### Atomic vs. Partial Success

- The batch create **may** support atomic or partial success.
- Synchronous batch create **must** be atomic.
- Asynchronous batch create **may** be atomic or partial success.

### Request Message

- A parent field **should** be included.
  - **Should** be required if only 1 parent is allowed.
  - **Should** identify the parent resource type.
- **Must** include a repeated field with the resources to create.
  - It **should** be named `requests`.
  - It **should** be required.
- The req msg **must not** contain any other required fields.

### Response Message

- **Must** include a repeated field with the created resources.

### Adopting Partial Success

- The default behavior for batch create **must** be retained.
- The req msg **must** have a bool return_partial_success field.
