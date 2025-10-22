# 🧾 Resource-Oriented Design

ROD is a pattern based on the following principles:

- Resources (nouns) are the building blocks of the API.
- Methods (verbs) provide operations on those resources.
- Stateless protocol: each client-server interaction is independent. Client and server both have clear roles.

When designing an API following ROD, we must consider the following:

- The resources that the API provides.
- The relationships between those resources.
- The schema of each resource.
- The methods each resource supports.

### Resources

- The API **should** be a resource heriarchy: each node is either a resource or a collection of resources.
- A collection contains resources of the same type.
- A resource may have any number of sub-resources.
- A resource may have any number of fields.

### Methods

- Usually, we will have a large number of resources and a small number of methods per resource.
- Methods can be standard (Get, List, Create, Update, Delete) or custom.
- Resource schema **must** be the same for all methods.
- A resource **must** support Get.
- A resource **must** support List, unless it is a singleton.
- The API **should** prefer standard methods over custom methods.

### Strong Consistency

- Following a Create → Get request **must** return the resource.
- Following an Update → Get request **must** return the updated resource.
- Following a Delete → Get request **must** return NOT_FOUND.

### Stateless Protocol

- The API **must** be stateless.
- Any individual request is independent of any other request.
- Resources exposed by the API are directly accessible.
- The server has the responsibility of persisting data.
- The clients have the responsibility of maintaining the application state.

### Cycle References

- The relation between resources **must** be acyclic.
- The relation between parent-child **must** be acyclic.
- Cyclic relations increase the complexity of resource management.
