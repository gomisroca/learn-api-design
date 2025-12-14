# Batch Methods: GET

- APIs **may** support Batch Get
- The RPC name **must** begin with `BatchGet`. The remainder **should** be the plural of the resource name.
- The request and response messages **must** match the RPC name, with Request and Response suffixes.
- The HTTP method **must** be `GET`
- The HTTP URI **must** end with `:batchGet`
- The URI path **should** represent the collection for the resource.
- The operation **must** be atomic. No partial success is allowed.

### Request Message

- A parent field **should** be included.
  - **Should** be required if only 1 parent is allowed.
  - **Should** identify the parent resource type.
- **Must** include a repeated field with the names of the resources to retrieve.
  - It **should** be named `names`.
  - If no resource names are provided, it **should** error with `INVALID_ARGUMENT`.
  - It **should** be required.
- Batch get **should not** support pagination.
- The req msg **must not** contain any other required fields.

### Response Message

- **Must** include a repeated field with the requested resources.
- The order in the response **must** match the order of the names in the request.
