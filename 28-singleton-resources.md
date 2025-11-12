# Singleton Resources

- An API **may** define a singleton resource.
- A singleton resource **must** always exist by virtue of its parent, with only one parent.
- Singleton names **must not** have a user-provided or system-generated ID. Their name includes the parent's name and a static segment.
- Singleton names **must** be singular.
- Singletons **may** parent oher resources.
- Singletons **must not** define the Create or Delete standard methods.
- Singletons **should** define the Get and Update methods.
- Singletons **may** define custom methods.
- Singletons **may** define the List method.
