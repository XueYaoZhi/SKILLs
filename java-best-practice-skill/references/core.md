# Core Correctness

- Equality: when overriding equals, check the hashCode contract, inheritance, and field mutability. Changing hash-relevant fields after inserting a key can break lookup. Do not mechanically generate equality based on a nullable ID for every entity.
- Resources: determine who creates, owns, and closes each resource. Prefer try-with-resources for closeable resources owned by the method. Do not assume the method should close caller-provided streams or container-managed clients.
- Inputs: validate business constraints at system boundaries and reuse established invariants internally rather than adding redundant checks. Empty collections versus null follow the API contract; inspect caller compatibility before changing it.
- Exceptions: retain causes and necessary context. Do not swallow failures or return false success. Avoid logging the same exception repeatedly or exposing credentials.
- Collections and immutability: an unmodifiable wrapper does not imply deep immutability. Check defensive copies and mutable elements when isolation from external changes matters.
- Construction: choose constructors, factories, builders, or records based on complexity and the target JDK; do not require factories or immutable classes universally.

Prioritize null and empty inputs, boundary values, exception paths, resource release, and existing callers during validation. Examples can explain behavior but cannot replace compilation in the actual project.
