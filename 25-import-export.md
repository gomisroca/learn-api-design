# Import and Export

- API **may** support import and export operations.
  - They **may** create multiple new resources.
  - They **may** populate data into a single resource.

### Multiple Resources

- Services **may** support importing and exporting multiple resources in/out of the API.
- **Should** implement a common pattern for import and export.
- The method **mmust** return a long running operation.
- The HTTP method **must** be `POST`. The body **must** be "\*".
- A `parent` field **should** be included in the URI.
- The URI suffix **should** be `:import` or `:export`.

### Data for a Single Resource

- Services **may** support importing and exporting data in/out of a single resource.
- **Should** implement a common pattern for import and export.
- The method **mmust** return a long running operation.
- The HTTP method **must** be `POST`. The body **must** be "\*".
- A field representing the resource **should** be included in the URI.
  - The field **should** be names after the resource.
- The URI suffix **should** include the verb and noun of the resource.
