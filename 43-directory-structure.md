# File and Directory Structure

- APIs defined in protocol buffers **must** use proto3 syntax.
- They **must** define each individual API in a single package, which **must** end with a version.

### File Names

- File names **must** be snake_case.
- APIs **should** have an obvious entry file. They **may** have a separate entry file per service.
- APIs with only one file **should** use a filename matching the name of the API.
- Services and their associated requests and responses **should** be defined in the same file.

### File Layout

- Higher level definitions **should** be placed before lower level definitions.
- In a proto file, components **should** be in the following order, separated by a blank line:
  - Copyright and License
  - Proto syntax statement
  - Proto package statement
  - Import statements
  - File-level option statements
  - Service definitions
  - Resource message definitions
  - RPC request and response message definitions
  - Any remaining message definitions
  - Any top-level enum definitions
