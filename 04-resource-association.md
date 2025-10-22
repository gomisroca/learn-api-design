# 🔗 Resource Association

- A resource **must** have at most one canonical parent.

### Many-to-one Associations

- If a resource has a many-to-one associations, it **must** choose one as its canonical parent.
- RPC **must** treat the `parent` field as required, and not add any additional required fields.
- RPC **should** include a `filter` field to filter by other associations.

### Many-to-many Associations

- The API **may** contain many-to-many associations.
- The API **should** use a repeated field to represent the association.
- The API **may** model a many-to-many with two one-to-many associations.
