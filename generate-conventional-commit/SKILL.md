---
name: generate-conventional-commit
description: Generate Conventional Commits messages from user-provided change descriptions or a specified Git diff. Use for requests to write, organize, or check commit messages; staged changes alone or ordinary code discussions do not trigger this skill.
metadata:
  version: "2.0.0"
---

# Generate Commit Messages

Deliver accurate, ready-to-copy commit messages. This skill generates text and permits read-only Git inspection; it does not stage, commit, reset, or push. Handle separately requested Git operations through the appropriate workflow.

## Gather Evidence

- Use a sufficient description or diff supplied by the user directly; do not require repository inspection.
- For repository-based requests, determine scope using [Read Changes](references/read-diff.md).
- Follow user and project conventions for language, type, scope, and length. Existing guidelines and a small sample of history may inform the result; incidental historical formatting is not a mandatory rule.
- File paths alone are not sufficient evidence of functional changes. Do not invent motives, issue numbers, test results, performance gains, or breaking changes.

## Generate

- Choose a type using [Format and Classification](references/message-rules.md). Use a business module or established project scope; omit it when no reliable scope exists and the project permits omission.
- Describe the main change in the subject. Add a body or footer only when it contributes information.
- For unrelated topics, suggest separate commits with corresponding messages; do not actually split commits. If the user requests one message, summarize the main intent without always favoring fix or chore.
- Explain missing evidence. A clearly labeled provisional candidate is acceptable; do not use chore to conceal uncertainty.

## Deliver

By default, output one code block containing the message. Explain only when the type is ambiguous, splitting is suggested, coverage is incomplete, or the user requests reasoning.

Before delivery, check consistency with evidence and project formatting, and correctly mark confirmed incompatible changes. Deliver completed text suggestions without requiring user confirmation to finish.
