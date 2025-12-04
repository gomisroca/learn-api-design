# API Versioning

- API interfaces **must** provide a major version number.
- APIs **must not** expose minor or patch version numbers.
- A new major version **must not** depend on a previous major version.
- An API surface **must not** depend on other APIs.
- Different versions of the same API **must** be able to work at the same time.
- For alpha or beta APIs, the stability level **must** be appended to the major version.
