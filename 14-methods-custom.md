# Methods: Custom

- Custom methods **should** only be used where there is no suitable standard method.
- Name of the method **should** be a verb followed by a noun.
  - **Must not** contain prepositions.
  - The verb **should not** contain any standard verbs (Get, List, Create, Update, Delete).
  - The name **must not** contains the term `Async`.
- HTTP verb **must** be `GET` or `POST`.
  - `GET` **must** be used for retrieving a resource.
  - `POST` **must** be used if the method has side-effects or mutates the resource.
- The URI **must** use a `:` followed by the custom verb. E.g. `:verb`.
- **Should** take a request msg matching the RPC name, with a `Request` suffix.
- **Should** return a response msg matching the RPC name, with a `Response` suffix.
