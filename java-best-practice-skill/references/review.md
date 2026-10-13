# Issue Reporting

For each actionable finding, provide severity, file and location, triggering conditions, actual impact, and a proposed repair. State unconfirmed assumptions and inspect callers when necessary.

Base severity on actual impact. Prioritize data corruption, security problems, incorrect behavior, and service failures; list maintenance suggestions separately. Not using factories, DDD, or a particular comment format is not automatically a defect.

Example:

> High: request completion does not clear thread-local user context. When the pool reuses the thread for a later request without user information, it may expose the previous request's identity. Clear or restore context at the end of the current request scope and verify isolation across two consecutive requests.

An actual report must include a real location and confirm the set, read, and cleanup paths. Do not present this example as an observed finding.

When no issues are found, state the inspection scope and validation limitations rather than claiming absolute correctness. Provide a full compliance matrix only when requested, allowing “not applicable” and “insufficient evidence” instead of forcing binary outcomes.
