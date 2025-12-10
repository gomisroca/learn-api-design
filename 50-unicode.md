# Unicode

- In API documentation, a character **must** be defined as a Unicode code point.
- All string length limits defined in comments **must** be measured and enforced in characters as defined above.
- APIs **may** use either code points or bytes as the unit for billing costs.
- Strings used as unique identifiers **should** limit input to the ASCII character set.
- The API **must** reject any inputs that are not in Normalization Form C.
- IDs **should not** start with a number.
- IDs **should** use a max length of 64 characters.
- Values **should** always be normalized to NFC.
- IDs **must** always be stored in NFC.
- Unique identifiers **must** be normalized to NFC.
