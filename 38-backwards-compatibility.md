# Backwards Compatibility

- Existing client code **must not** be broken by updating to a minor or patch version.
- Old client **must** be able to work against newer servers (within the same major version).
- Three types of compatibility:
  - Source compatibility: Code written against an older version **must** compile against a newer version.
  - Wire compatibility: Code written against an older version **must** be able to communicate with a newer version.
  - Semantic compatibility: Code written against an older version **must** continue to receive what seems reasonable.

### Adding Components

- New components **may** be added to the API in the same major version.
- Old code **must** continue to be treated the same as before.
- New required fields **must not** be added to existing req msgs or resources.
- Enum values **may** be freely added to enums only used in req msgs.
- Enums used in res msgs or resources expected to receive new values **should** document this. Enum values **may** still be added in this situation.

### Removing or Renaming Components

- Existing components **must not** be removed from the API in the same major version.

### Moving Components between Files

- Existing components **must not** be moved between files.

### Moving into oneofs

- Existing components **must not** be moved into or out of oneofs.

### Changing the Type of a Field

- Existing fields **must not** be changed to a different type.

### Changing String Length

- Apis **should** avoid increasing the upper bound of a string length.
- Apis **may** pad out values with filler characters if necessary. This **must** be documented.

### Changing Resource Names

- Existing resources **must not** be renamed.
- The set of valid resource names **should not** be changed.
