# Unreachable Resources

- If a method can partially fail due to resources being temporarily unavailable, the service **must** return a field indicating this.
- The field **must** be a repeated string called unreachable.
- The field **must** contain the resource names that are unreachable.
- The field **must** contain service-relative names.
- The res **must not** provide any other information about the issue.
- The service **must** provide a way to make a more specific request.
- The resource names in the unreachable field **may** be heterogeneous.
- unreachable **must** be an unordered list.
