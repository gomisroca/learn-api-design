# Time and Duration

- Time fields **should** use common component for time and duration types.

### Timestamps

- Timestamps **should** use the `timestamp` type.
- Timestamp fields **should** have names ending in `_time`. (e.g. `create__time`)
- Timestamp fields of an activity (create, update, etc.) **should** use the `{imperative}_time` format. (e.g. `create_time`)

### Durations

- Duration fields **should** use the `duration` type.

### Relative Time Segments

- Relative time segments fields **should** end with `_offset`.
- The field **must** have a comment noting the point the offset is relative to.

### Civil Dates and Times

- Calendar dates or wall-clock times **should** use the appropriate types.
- Civil date fields **should** end with `_date`.
- Civil time fields **should** end with `_time`.
