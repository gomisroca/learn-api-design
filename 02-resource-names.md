# 🥸 Resource Names

- Each resource **must** have a unique name and ID.
- Resource name components **should** alternate between collections identifiers (e.g. `publishers`, `books`, `users`) and resource IDs (e.g. `123`, `les-miserables`, `vhugo89`).
- Resource names **must** use `/` to separate segments of the name.
- Resource names **should** only use characters available in DNS names.
- Resources **must** expose a `name` field.

### Collection Identifiers

- Collection ids **must** be the plural form of the resource name (e.g. a collection of `Book` resources is named `books`).
- Collection ids **must** be concise.
- Collection ids **must** be in camelCase.
- Collection ids **must** start with a lowercase letter and use only ASCII letters and numbers.
- Collection ids **must** be unique within their hierarchy.

### Resource Identifiers

- The API **must** document the format of resource ids.
- The API **may** provide programmatic aliases for common lookup patterns.
- All data returned from the API **must** use the canonical resource name.
- Sometimes, the API **should** use the full resource name (e.g. `//library.googleapis.com/publishers/123/books/les-miserables`).
- Resource URIs are the full name of the resource, including the protocol (e.g. `https://library.googleapis.com/publishers/123/books/les-miserables`).
- First field of a resource **should** be the resource name. It **must** be a string and **must** be called `name`.
- When retrieving a single resource, the first field of the request message **should** be the resource name and **should** be called `name`.
- When retrieving resources from a collection, the first field of the request message **should** be the collection name and **should** be called `parent`.
