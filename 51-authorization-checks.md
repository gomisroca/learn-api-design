# Authorization Checks

- Services **must** check authorization before validating any request.
- An operation **may** require multiple permissions.
- If authorization fails, the service **must** return a `PERMISSION_DENIED` error.
- If the resource is not found, but the authorization check on the parent passes, the service **must** return a `NOT_FOUND` error.
