# States

- Resources **should** use an enum to define their state. It **should** be called State.
- The field referencing the State enum **should** be Output onlt.
- APIs **should not** allow the State enum to be updated directly.
- It **should** instead use custom state transition methods.

### State Transition Methods

- The name of the method **should** be a verb followed by the singular form of the resource name.
- The req msg **must** match the RPC name.
- The res msq **should** be the resource itself.
- The HTTP method **should** be POST.
- The HTTP URI **must** use a `:` followed by a custom verb.
- The body clause **must** be `*`.
- If state transition is not allowed, the service **must** return a `FAILED_PRECONDITION` error.
