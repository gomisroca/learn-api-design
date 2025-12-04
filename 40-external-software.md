# External Software Dependencies

- Services with external dependencies **should** allow users to create resources with any supported version of the dependency.
- Services **should not** indefinitely allows users to create resources with unsupported versions of the dependency.
- Services **should** allow previously-created resources to remain.
- Services **may** warn users if they use unsupported versions of the dependency.
- Services **should not** proactively remove resources that use unsupported versions of the dependency.
