# Pagination

- RPCs returning collections **must** provide pagination at the outset.
- Req msgs for collections **should** include an int_32 `page_size` field.
  - The field **must** be optional.
  - If not specified, the API must choose an appropriate default. It **must not** return an error.
  - If the `page_size` is greater than the max permitted, the API **must** return an `INVALID_ARGUMENT` error.
  - The API **may** return fewer results than requested.
- Req msgs for collections **should** include a string `page_token` field.
  - The field **must** be optional.
  - If the user changes the `page_size`, the API **must** honor the new `page_size`.
  - If any other argument changes, the API **should** return an `INVALID_ARGUMENT` error.
- The response **must not** be a streaming response.
- Response messages for collections **should** define a `next_page_token` field.
  - If the end of the collection has been reached, the field **must** be empty.
  - If there are more results, the API **must** return a non-empty `next_page_token`.
- Response messages for collections **may** define a `total_size` field.
  - The total **may** be an estimate.

### Skipping Results

- Requests **may** define an int_32 `skip` field.
- The field **must** refer to the number of results to skip, not pages.

### Opacity

- Page tokens **must** be opaque strings. They **must not** be user-parseable.

### Expiring Page Tokens

- If the API store page tokens, it **may** expire them a reasonsable time after they are issued.
