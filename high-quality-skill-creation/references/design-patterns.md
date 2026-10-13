# Choose a Structure for the Task

## Simple Transformations

For example, generating a commit message from an existing change description needs only input requirements, output format, and evidence boundaries. It does not need tools, installation questions, or a confirmation loop.

## Multiple Task Modes

For Java implementation, review, and refactoring, share scope and validation principles in the entrypoint. Read references for concurrency, performance, or architecture only when relevant. Do not turn a small change into a full architectural review.

## External Operations

For deployment, specify the target environment, authorization boundaries, success evidence, and stopping conditions. Before retrying a request with side effects, determine whether the previous attempt succeeded. Retry policies cannot replace authorization.

## Entrypoint Example

This is an illustrative template. Replace its content when creating a skill; do not leave template markers in the delivered files.

```yaml
---
name: summarize-release-changes
description: Generate release notes from changes for a specified version; use for release summaries, without performing publication.
---
```

The body should explain how to determine the version range, separate user-visible changes from internal maintenance, and handle insufficient evidence. Split references only when substantial audience-specific guidance warrants it.

## Common Problems

| Problem | Improvement |
| --- | --- |
| Every skill requires seven validation layers and user confirmation | Choose checks proportional to task risk |
| Every failure results in another prohibition | First inspect missing context, tool contracts, and inputs |
| File or line counts serve as proof of quality | Evaluate correctness, false triggers, extra interaction, and resource cost |
| A tool name or personal path is mandatory | Declare such dependencies only for an explicitly platform-specific skill |
| Linked documents do not exist | Verify actual paths in the delivered package |
