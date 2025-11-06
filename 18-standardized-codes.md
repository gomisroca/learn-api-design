# Standardized Codes

- Many common concepts, lieke languages, currencies, and countries, have common codes (CC).
- Fields where a CC is suitable **should** use said code.
- CC fields **must** use the appropiate data type for the code.
  - **Should not** use enums.
  - **Must** indicate the standard used.
- Field name **should** end in `_code` or `_type`.
- If accepting user input, validation **should** be case-insensitive.

### Content Types

- Fields representing content or media type **must** use IANA media types.
  - The field **should** be called `mime_type`.

### Countries and Regions

- Fields representing countries or regions **must** use Unicode CLDR region codes.
  - The field **should** be called `region_code`.

### Currency

- Fields representing currencies **must** use ISO 4217 currency codes.
  - The field **should** be called `currency_code`.

### Language

- Fields representing languages **must** use IETF BCP-47 language codes.
  - The field **should** be called `language_code`.

### Time Zones

- Fields representing time zones **must** use IANA time zone codes.
  - The field **should** be called `time_zone`.
