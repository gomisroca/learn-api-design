# Jobs

- API **may** define a Job resource to represent a task with distinct setup, config and execution.
- The name of the resource **must** end with `Job`.
  - The prefix should be a valid RPC name, with a verb and noun.
- The service **should** define all five standard methods.

### Run Method

- The service **should** define a `Run` method to execute the job immediately.
- The RPC's name **must** begin with `Run`. The rest **should** be the singular form of the resource name.
- The request message **must** be the RPC name with a `Request` suffix.
- The method **should** return a long running operation.
- The HTTP method **must** be `POST`.
- The URI path **should** contain a single `name` variable.
- The URI path **must** end with `:run`.
- Errors that prevent the execution from starting **must** return an error response.
- Errors during execution **may** be placed in the metadata message.

### Run Request Message

- Run methods implement a common request message pattern.
- A singular `name` string field **must** be present.
