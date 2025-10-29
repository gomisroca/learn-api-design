# Declarative-friendly Interfaces

- Many services need to interact with DevOps tools, which are declarative: they specify desired outcomes, instead of actions to take.
- Declarative-friendly resources (DFRs) **must** use consistent standard methods for managing lifecycles.
- DFRs **should** follow the declarative-friendly style.
- If a DFR takes time to update, it **should** include a bool `reconciling` field.
  - `reconciling` **must** be output only.
  - `reconciling` **must** be `true` if the resource is currently being reconciled.
