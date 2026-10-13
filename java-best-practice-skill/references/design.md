# Design Tradeoffs

Identify whether the project uses simple layering, transaction scripts, a domain model, or another approach. Classes or interfaces alone do not justify introducing a full DDD architecture.

- Interfaces: introduce abstractions for real substitution points, module boundaries, or test isolation. Not every class needs an interface.
- Behavior preservation: establish observable contracts before refactoring, including inputs, outputs, exceptions, transactions, ordering, serialization, and call sequence.
- DDD: check aggregate boundaries, business invariants, and ubiquitous language when the project adopts DDD or the user requests it. Repository placement and framework annotations follow project conventions, not universal correctness prohibitions.
- Consistency: determine consistency and compensation requirements before changing cross-aggregate or cross-service operations. Do not switch to asynchronous events solely to achieve decoupling.
- Simple business logic: DTOs, CRUD services, and mappings may remain simple. A lack of business behavior does not automatically make a model defective or require redesign.
- Patterns: introduce strategies, factories, and other patterns only when variation, complexity, or duplication warrants them. Explain the concrete problem solved.

Architectural feedback should identify dependencies or change scenarios and their impact. For large migrations, describe boundaries, compatibility, and validation before implementation; do not include them incidentally in a local repair.
