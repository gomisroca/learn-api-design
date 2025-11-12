# Resource Freshness Validation

- A resource **may** include an `etag` field
- The field **must** be a string, and **must** be called `etag`.
- The field **should not** be given any behavior annotations.
- The field **must** be provided by the server on output.
- If the user sends back an etag that matches the current etag, the service **must** permit the request.
- If the user sends back an etag that does not match the current etag, the service **must** send an ABORTED error response.
- If the user doesn't send any etag, the service **should** permit the request.

### Declarative-friendly Resources

- A resource that is declarative-friendly **must** include an `etag` field.

### Etags on Request Methods

- In some cases, the etag needs to be on a request msg, rather than the resource itself.
- In this case, the `etag` field **should** be given a behaviour annotiation - either REQUIRED or OPTIONAL.
- The etag field **may** be used on custom methods.

### Strong and Weak Etags

- Strong etags means two resources bearing the same etag are byte-for-byte identical.
- Weak etags means two resources bearing the same etag are equivalent, but may differ in non-important ways.
- Resources **may** use strong or weak etags.
- Weak etags **must** have a `W/` prefix.
