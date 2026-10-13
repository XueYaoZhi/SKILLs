# Performance Analysis

Establish data scale, latency or throughput goals, and existing measurements. Without data, describe risks or hypotheses rather than claiming fixed speedups.

| Area | Checks and tradeoffs |
| --- | --- |
| Data access | Identify N+1 access and large result sets. Select batching, pagination, or streaming for the workload, considering parameter limits, ordering, and transaction consistency |
| Caching | Design capacity, invalidation, and eviction around key space, object sizes, and freshness. A finite fixed key space does not mechanically require TTL |
| Allocation | Inspect allocation rates and lifecycles on hot paths; do not prohibit ordinary object creation inside loops |
| Strings | Consider StringBuilder for substantial repeated accumulation; do not rewrite simple concatenation just for compliance |
| JVM | Start from the actual JDK, container limits, and runtime metrics. Do not change GC or heap settings merely to avoid defaults |
| Connections and clients | Reuse expensive resources according to library thread safety and lifecycle contracts. Measure pool sizing against downstream capacity and wait times |
| I/O | Check connection, read/write, and overall deadlines. Buffering benefits depend on access patterns and underlying implementations |
| Reflection | Evaluate caching or alternatives using hotspot evidence; do not universally prohibit framework proxies or reflection |

Validate correctness, representative inputs, warmup, and resource costs alongside performance. Microbenchmarks do not directly establish whole-service throughput. Explicitly state when no measurement was performed.
