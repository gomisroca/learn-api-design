# Standard Fields

- Standard fields **should** be used to describe their corresponding concept.
- Standard fields **should not** be used for any other purpose.

### Resource Names and IDs

- Every resource **must** have a `name` string field.
- `name` **should** the first field in the resource.
- In a List/Create request, there **should** be a `parent` string field.

- `display_name` **must** be a mutable, user-settable field.
- `display_name` **should** be a string field.
- `display_name` **should not** have uniqueness requirements.
- `display_name` **should** be limited to <= 63 characters.
- `title` **should** be the official name of an entity.
- `given_name` **must** refer to a human or animal's given name.
- `family_name` **must** refer to a human or animal's family name.
- `create_time` **must** be the time the resource was created.
- `update_time` **must** be the time the resource was last updated.
- `delete_time` **must** be the time the resource was deleted.
- `expire_time` **should** be the time the resource will be obsolete.
- `purge_time` **should** be the time the resource will be purged.
- `annotations` **must** use the kubernetes limits.
- `ip_address` **must** use type string. It **must** specify the IP format.
