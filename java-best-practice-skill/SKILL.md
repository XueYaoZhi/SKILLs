---
name: java-best-practice-skill
description: Check correctness, resource lifecycles, concurrency, and design tradeoffs during Java implementation, review, and refactoring. Use for actual Java code work or explicit Java best-practice advice; do not expand scope merely because DDD, a code path, or JVM is mentioned.
metadata:
  version: "2.0.0"
---

# Java Implementation and Review

Solve the user's problem using code evidence while preserving the project's architecture and compatibility. Domain guidance directs inspection; it does not replace requirements or actual validation.

## Establish Context

- Identify implementation, review, repair, or refactoring intent. Proceed directly when the context is clear.
- In repository tasks, inspect applicable instructions, build files, target JDK, framework versions, and neighboring implementations. Do not upgrade dependencies without authorization or introduce APIs unsupported by the target version.
- Determine change scope and existing uncommitted edits. Refactoring preserves external behavior by default and does not include incidental architecture migration.
- For snippets, state the analysis scope. Read additional callers or configuration, or ask for them, when they could change the conclusion.

## Read References as Needed

| Current concern | Reference |
| --- | --- |
| Equality, collections, exceptions, resource ownership, input boundaries | [Core Correctness](references/core.md) |
| Shared state, asynchronous tasks, executors, ThreadLocal | [Concurrency](references/concurrency.md) |
| Module boundaries, domain models, transactions, interface changes | [Design](references/design.md) |
| Latency, memory, database access, caching, JVM tuning | [Performance](references/performance.md) |

Read only relevant documents. Small changes do not automatically require every rule or an architectural review. Disclose missing references and complete sufficiently supported work; do not claim to rely on unread material.

## Execute and Validate

- Implementation or repair: make the smallest sufficient change. Comments explain business reasons and non-obvious constraints; do not require skill rule identifiers.
- Review: report locatable issues with concrete triggers and impact. Separate suggestions from defects, and do not automatically edit files.
- Refactoring: preserve public contracts, transaction boundaries, and exception semantics. Fix related defects within authorized scope; describe changes outside that scope separately.
- Validate with existing project builds and tests, prioritizing affected modules and important behavior. For concurrency, check atomicity and lifecycles. Support performance conclusions with benchmarks or runtime metrics where possible.
- Accurately report unverified work when tools or dependencies are missing. Diagnose and repair failures; after repeated identical failures, preserve progress and explain the blocker rather than rewriting blindly or reverting user edits.

## Output

For implementation and refactoring, explain changes, reasons, actual validation, and remaining limitations. For reviews, use [Issue Reporting](references/review.md), prioritizing findings and evidence rather than irrelevant item-by-item compliance declarations.
