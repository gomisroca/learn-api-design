# Generic Fields

- A service **may** introduce generic fields where necessary.
- A service **should** attempt to introduce the "least generic" approach to satisfy the use case.

### Oneof

- oneof **may** be used to introduce a type union.
- oneof **may** be used with the same type to represent a semantic difference between options.
- A service **should** prefer oneof over other generic options.

### Maps

- Maps **may** be used in situations where many values of the same type are needed, but the keys are unknown or user-defined.

### Struct

- Struct **may** be used to represent arbitrary nested JSON.

### Any

- Any **may** be used to send an arbitrary serialized protocol buffer and a type definition.
- Any **should not** be used unless there are no other options.
