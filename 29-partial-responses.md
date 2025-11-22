# Partial Responses

- APIs **may** support partial responses.

### Field Masks

- Fields masks can be used to give the user control over which fields are returned. The API **should** support the mask in a side channel.
- Field masks **should not** be specified in the request:
  - The field mark param **must** be optional.
  - A value of `*` **should** be supported. It **must** return all fields.
  - If a value of `*` is accepted, it **must** be the default.

### View Enumeration

- APIs **may** support partial responses with view enums.
- The enum **should** be specified as a `view` field.
- The enum **should** be named ending with `-View`.
- The enum **should** have at minimum values `BASIC` and `FULL`.
  - It **may** have more values.
- The `UNSPECIFIED` value **must** be valid and **must** be documented.
- For List RPCs, the default value **should** be `BASIC`.
- For Get, Create, Update, and Delete RPCs, the default value **should** be `BASIC` or `FULL`.
- The enum **should** be defined at the top level.
- The API **may** add fields to a view over time.
- The API **must not** remove fields from a view.
