# Automatic Retry Configuration

- Clients **should** automatically retry safe requests.
- Clients **should not** automatically retry transactional requests.
- Clients **should not** automatically retry requests in which repetition would cause unintended side effects.

### Retryable Codes

- If retryable, clients **should** retry the code UNAVAILABLE.

### Non-Retryable Codes

The following codes **should not** be retried:

- OK
- CANCELLED
- DEADLINE_EXCEEDED
- INVALID_ARGUMENT
- DATA_LOSS
- RESOURCE_EXHAUSTED
- INTERNAL
- UNKNOWN
- ABORTED
- NOT_FOUND
- ALREADY_EXISTS
- PERMISSION_DENIED
- UNAUTHENTICATED
- UNAUTHORIZED
- FAILED_PRECONDITION
- OUT_OF_RANGE
- UNIMPLEMENTED
