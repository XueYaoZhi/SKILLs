# Failure Handling

Distinguish missing inputs, unavailable tools, transient failures, and operations that succeeded but lost their response.

- Missing inputs: continue independent work and ask only for facts that affect the result.
- Unavailable tools: use an equivalent authorized tool. If none exists, deliver usable work and explain the limitation.
- Transient read-only failures: allow a small number of justified retries. Stop after repeated identical failures and explain the cause.
- Unknown write or external operation status: read back state or query the operation ID before repeating writes, payments, publication, or messages.
- Validation failures: diagnose the specific cause, fix affected parts, and retest. Do not remove failing cases merely to pass.
- Rollback: restore only clearly identifiable changes from the current task and preserve the user's preexisting edits. If they cannot be reliably distinguished, preserve the current state and explain why.

Choose retry counts, backoff intervals, and idempotency mechanisms from the target system's contract rather than universal constants. Do not reduce query scope or discard data and then describe an incomplete result as successful.
