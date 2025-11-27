# Soft Delete

- APIs **may** support soft delete.

If a resource supports soft delete:

- The Delete method **must** mark the resource as deleted, but not actually delete it.
- The Delete method **should** return the resource.
- The resource **should** have a `delete_time`and `purge_time` field.
- If the resource includes a `state` field, it **should** be set to `DELETED`.

### Undelete

- If a resource supports soft delete, it **should** provide an Undelete method.
- The HTTP verb **must** be POST.
- The body clause **must** be `*`.
- The res msg **must** be the resource itself.

### Undelete Request Message

- A name field **must** be specified. It **should** be called `name`.
  - The field **should** be required.
  - The field **should** identify the resource type.
  - The field **should** be documented.
- The req msg **must not** include any other required fields.

### Long-running Undelete

- If an undelete takes a long time, the API **should** use a long-running operation.
- The response type **must** be the resource itself.
- Both the `response_type` and `metadata_type` **must** be specified.

### List and Get

- Soft-deleted resources **should not** be returned by List by default.
- Get methods **should** return soft-deleted resources if they are requested.

### Errors

- If the user cannot access a resource, the service **must** return a PERMISSION_DENIED error. Permission **must** be checked before checking if the resource exists.
- If the user is authorized, but the resource doesn't exist, the service **must** return a NOT_FOUND error.
- If a soft delete is called on a resource that is already deleted, the service **must** suceed if `allow_missing` is true, and **should** return a NOT_FOUND error otherwise.
- If Undelete is called on a non-deleted resource, the service **must** return a ALREADY_EXISTS error.
