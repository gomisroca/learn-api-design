# Request Identification

- Sometimes APIs need unique, user-provided identifiers for requests.
- APIs **may** add a `request_id` field to the request message.
- Providing a Request ID **must** guarantee idempotency.
- Request IDs **should** be optional.
- Request IDs **should** be able to be UUIDs. They **may** only be UUIDs, but this restriction **must** be documented.
