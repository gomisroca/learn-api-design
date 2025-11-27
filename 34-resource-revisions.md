# Resource Revisions

- APIs **may** store a revision history for a resource.
- It **should** abstract resource revisions as nested collection of the resource.
- The message **must** be annotated as a resource.
- The message name **must** be `{ResourceType}Revision`.
- The resource revision **must** contain a `snapshot` field with the parent type.
- The resource revision **must** contain a `create_time` field.
- The resource revision **may** contain a repeated `alternate_ids` field, which contains a list of ids the revision is also known by.
- Revisions for a specific resource **must** be under the name `revisions`. i.e. `publishers/123/books/les-miserables/revisions/c7cfa2a8`

### Creating Revisions

- APIs **may** use any strategy for creating resource revisions.
- It **must** be documented in the API.

### Server-specified Aliases

- Services **may** reserve specific ids as aliases. i.e. `latest`
- If a `latest` alias is specified, the service **must** return the latest revision.

### User-specified Aliases

- APIs **may** allow the user to specify aliases for revisions.
- The req msg **must** have a `name` field.
  - The field **must** be required.
  - The field **must** identify the resource type it refers to.
- The req msg **must** have a `alias_id` field.
  - The field **must** be required.

### Rollback

- APIs **should** support rollback to a specific revision with a custom `Rollback` method.
  - The method **must** use the POST HTTP verb.
  - The method **should** return a resource revision.
- The req msg **must** have a `name` field.
  - The field **must** be required.
  - The field **must** identify the resource type it refers to.

### Standard Methods

- Standard methods **must** be supported for resource revisions.
- List methods **must** list the revisions in reverse chronological order.
  - The user can supply a `order_by` field to change the order.
