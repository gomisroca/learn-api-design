# Errors

- Services **must** use caninocal error codes.
- Error msgs **should** help understand and resolve the issue.
  - They **should not** assume the user is familiar with the API.
  - They **should** be brief.
  - Additional info **should** be provided in the `details` field.
- Dynamic aspects of the message **must** be included as metadata.
- Messages **should** use simple language.
- The error status code **must** be a valid numeric value.
- Each type of payload **must** be included at most once.
- Services **should** use standard payloads when feasible.
- All error responses **must** include an ErrorInfo within details.
- APIs **should not** support partial errors.
- Methods requiring partial errors **should** use long-running operations and put the partial error in the metadata.
- On permission denied, the service **must** return a 403 status code.
- Permission **must** be checked before performing the operation.
