# 🪟 HTTP and gRPC Transcoding

- APIs **must** provide HTTP definitions for each RPC.
- When providing a bidirectional streaming method, the API **should** provide an alternative method.
- When using protocol buffers, each RPC **must** define the HTTP method and path.
  - The first key corresponds to the HTTP method.
    - **Must** use the prescribed HTTP verb.
    - **Should** use the prescribed HTTP verb for custom methods.
    - **Should not** use `put` or `custom`.
  - The corresponding value is the URI.
    - URIs **must** use the `{foo=bar/*}` syntax.
    - URIS **may** use nested fields for their variable names.
    - URIS **must** use `*` char to represent IDs.
  - The `body` key defines the request body.
    - **Must not** define a `body` at all if the method is GET or DELETE.
    - **Must** use the prescribed `body` for CREATE and UPDATE methods.
    - **Should** use the prescribed `body` for custom methods.
    - **Must not** contain a nested field.
    - **Must not** be the same as the URI.
    - **Must not** be a repeated field.
    - **Should not** use `json_name` annotation.

### Multiple URI Bindings

- RPCs **may** define any number of URI bindings.
- RPCs **must not** define an additional binding within an additional binding.
- The `body` clause **must** be identical for all bindings.
