# Concurrency Checks

## State and Atomicity

First establish whether objects are actually shared across threads. volatile provides visibility but does not make `count++` or check-then-update operations atomic. Consider concurrent collection atomic APIs for single-key updates; invariants spanning multiple keys or objects require appropriate synchronization or transactions.

## Executors and Lifecycles

Choose executors based on CPU/I/O characteristics, submission rate, queue limits, and downstream capacity. Do not universally prohibit Executors or the common pool. Evaluate isolation and backpressure for blocking or unbounded workloads. Virtual threads do not make downstream resources unlimited; check the target JDK before using them.

Only resource owners close executors. Do not close shared or container-managed executors after an individual invocation. Handle cancellation, interruption, cleanup, and waiting policies when stopping tasks. A Future timeout does not necessarily stop the underlying operation.

## Asynchronous Completion

Check whether exceptions are observed, which layer supplies the timeout budget, and what callers receive on failure. Do not impose an independent timeout on every already-completed computation-only Future. Verify I/O and Future timeouts separately.

## ThreadLocal

Clear request-scoped context on reused threads at the end of the request, usually in finally, rather than waiting for the pool thread to exit. Nested scopes may need to restore previous context instead of unconditionally removing it. Check that cross-thread propagation is explicit and preserves required isolation.

Validate racing interleavings, compound updates, cancellation, and context left after task completion. A single sequential test cannot prove thread safety.

API references, subject to the project's actual JDK: [ThreadLocal](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/ThreadLocal.html) and [CompletableFuture](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/CompletableFuture.html).
