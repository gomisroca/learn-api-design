# Methods: Create

- APIs **should** provide a `Create` method for resources.
- RPC name **must** begin with the word `Create` followed by the singluar resource name. E.g. `CreateUser`.
- The request msg **must** match the RPC name, with a `Request` suffix.
- The response msg **must** be the resource itself.
- The HTTP Verb **must** be `POST`.
- The collection where the resource is created **should** map to the URI path.

### Request Message

- A `parent` field **must** be included unless the resource is a top-level resource.
- A `{resource}_id` field **must** be included for management plane resources, and **should** be included for data plane resources.
- The resource field **must** be included and **must** map to the POST body.
- The request msg **must not** contain any other fields.

### Long-running Create

- If the resource takes a while to create, the API **should** use a long-running operation.
- The response type **must** be the resource itself.

### User-specified IDs

- On the management plane, the API **must** allow the user to specify the ID of the resource.
- On the data plane, the API **should** allow the user to specify the ID of the resource.
