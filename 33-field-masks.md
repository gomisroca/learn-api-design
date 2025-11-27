# Field Masks

- Field masks **must** always be relative to the resource.

### Read-write consistency

- Read-write behavior for field masks **must** be self-consistent if a mask is present.
- If a masked resource is updated and then read, the exact same data **must** be returned.
- If a masked resource is read and then updated with the return data and the same mask **must** be a no-op.

### Specifying Specific Fields

- Field masks **must** allow specifying specific fields using the dot notation.

### Map Fields

- Field masks **may** permit the specification of fields in a map using the dot notation.
- Fields masks **should** support string keys with problematic characters escaped.

### Wildcards

- Field masks **may** support wildcards with the `*` character on repeated fields or maps.

### Output Only Fields

- The service **must** ignore any output only fields provided as input.

### Invalid Field Masks Entries

- On read, field masks **may** ignore entries that point to a value that can not exist.
- On write, field masks **should** return an INVALID_ARGUMENT error if an entry is invalid.
