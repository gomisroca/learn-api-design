# Reading Across Collections

- APIs **may** support reading across collections by allowing the user to specify a `-` as wildcard. Ex: `/v1/publishers/-/books?filter=...`
- The URI pattern **must** still be specified with `*` and permit the collection name to be specified.
- It **must** be documented that the wildcard is supported.
- It **may** support the wildcard even if the child resources ids are not unique.
- It **must not** the wildcard on Get reqs if the child resources might have collisions.
- Cross-parent reqs **should not** support `order_by`. If they do, the filed **must** be documented.

### Unique Resource Lookup

- APIs **may** allow the user to specify the wildcard collection id.
- The URI pattern **must** still be specified with `*` and permit the collection name to be specified.
- It **must** be documented that this is supported.
- The resource id **must** be unique within the parent collections.
