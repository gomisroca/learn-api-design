# Methods: LIST

- APIs **must** provide a `List` method for resources, unless the resource is a singleton.
- RPC name **must** begin with the word `List`.
- Requests/Responses **must** match the RPC name, with a `Request`/`Response` suffix.
- The HTTP Verb **must** be `GET`.
- The collection being listed **should** map to the URI path.

### Request Message

- The parent `parent` field **must** be included unless the resource is top-level.
- The `page_size` and `page_token` fields **must** be included.
- The `page_token` field **must** be included on all list request msgs.
- The request msg **may** include fields for filtering the list.
- The request msg **must not** contain any other fields.

### Response Message

- The response msg **must** include a repeated field corresponding to the resources.
- The response msg **must** include a `next_page_token` field.
- The msg **may** include a `total_size` int32 field.

### Ordering

- Values **should** be a comma separated list of fields. F.e: "foo,bar".
- Space characters are insignificant.
- Subfields are specified by dot notation.
- The resulting list order **should** be based on the field type's natural comparator e.g. numerics ordered numerically, strings ordered lexicographically.

### Filtering

- List methods **may** allow clients to specify filters.
