# Filtering

- APIs **may** may support filtering on List methods.
- If allowed, the req msg **should** include a `filter` string field.

### Literals

- Literals appearing alone **should** be matched anywhere it may appear in an object's field values.
- A service **may** choose to only consider certain fields.
  - If so, it **must** document which fields are supported.
  - It **may** include new fields over time, but **should** do so judiciously.

### Logical Operators

- Filtering **should** provide the binary operators `AND`, `OR`, and `NOT` (`-`).

### Comparison Operators

- Filtering **should** provide the comparison operators `=`, `!=`, `>`, `>=`, `<`, `<=` for string, numeric, timestamp and duration fields.
- It **should not** provide them for boolean or enum fields.

### Traversal Operator

- Filtering **should** provide the traversal operator `.` for traversing through a message, map or struct.
- Traversal **must** be written using the field names from the resource.
  - The service **may** specify a subset of fields to be supported for traversal.
- If the user attemps to traverse through a field that does not exist, the service **should** return an INVALID_ARGUMENT error.
  - The service **may** allow traversal to undefined keys.
  - If so, it **should** document the behaviour in this situation.

### Has Operator

- Filtering **should** provide the has operator `:`.

### Functions

- An API **may** define a function using the call(arg...) syntax for filtering.
- The function **must** be documented in the API.

### Limitations

- A service **may** specify limitations for filter queries.
- If so, it **must** document the limitations, and **must not** violate them.

### Validation

- If an invalid filter is specified, the service **should** return an INVALID_ARGUMENT error.
