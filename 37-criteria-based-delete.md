# Criteria-based Delete

- APIs **may** implement a Purge method that deletes a large number of resources based on a criteria.
- This **should** be done if Batch Delete is insufficient.
- The RPC's `name` **must** being with the word `Purge`.
- The req msg **must** match the RPC name, with `Request` appended.
- The HTTP verb **must** be POST.
- The body **must** be `*`.
- The URI path **should** represent the collection for the resource.
- The `parent` field **should** be included in the URI.

### Request Message

- A `parent` field **should** be included, unless the resource is top-level.
  - The field **should** be required.
  - The field **should** identify the resource type.
- A `filter` field **must** be included.
  - The field **should** be required.
  - A wildcard `*` **may** be supported for deleting everything.
- A `force` field **must** be included. If unset, the API **must** return a count of the resources that would be deleted, without actually deleting them.

### Response Message

- A `purge_count` field **should** be included. It **may** be an estimate, but **should** be documented if so.
- A repeated `purge_sample` **should** be included. If `force` is true, it **should not** be populated.
  - The sample **should** be sufficient size to catch most cases.
  - The sample **may** be random or deterministic.
  - The field **should** identify the resource type it refers to.
