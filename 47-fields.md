# Fields

- UUID4 format **must** only be used on string type fields.
- IPv4 format **must** only be used on string type fields.
- IPv6 format **must** only be used on string type fields.
  - It **may** be normalized to lowercase with zeroes.
  - As such, comparisons **must not** be done via text comparison.
