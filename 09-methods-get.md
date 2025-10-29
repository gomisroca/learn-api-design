# Methods: GET

- APIs **must** provide a `GET` method for resources.
- RPC name **must** begin with the word `Get`.
- The request msg **must** match the RPC name, with a `Request` suffix.
- The response msg **must** be the resource itself.
- The HTTP Verb **must** be `GET`.
- The URI **should** contain a single variable field corresponding to the resource name.
  - The field name **should** be `name`.

### Request Message

- Resource name field **must** be included. It **should** be called `name`.
- The commment for `name` **should** document the resource pattern.
- The request msg **must not** contain any other fields.
