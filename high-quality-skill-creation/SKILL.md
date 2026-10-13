---
name: high-quality-skill-creation
description: Create, review, or improve Agent Skill instructions, supporting resources, and validation plans. Use when the user explicitly requests a skill or improvements to its execution; not for ordinary document writing or business code implementation.
metadata:
  version: "2.0.0"
---

# Create Reliable Skills

Provide task knowledge and operational constraints the model would otherwise lack. Measure quality by task outcomes, not length, directory count, or the number of mandatory steps.

## Determine Scope

- Infer the target task, inputs, outputs, and exclusions from the request and available materials. Do not ask questions already answered.
- Clarify only when missing information materially affects the result, authorization, or destination. Use and state reasonable defaults for reversible details.
- Before updating a skill, read its entrypoint, relevant references, and callers. Preserve effective behavior and user customizations; address evidenced problems.
- Respect the requested destination. Otherwise, identify the host's skill discovery rules. If the host is unknown, deliver in the workspace without claiming installation or automatic activation.
- Use file, terminal, and interaction tools actually available in the environment; do not assume tool names or a particular shell.

## Write

1. Include `name` and `description` in the YAML frontmatter of `SKILL.md`. Match the folder name, use lowercase letters, digits, and hyphens, and keep the name under 64 characters. Describe capabilities and invocation conditions without attracting unrelated tasks through keywords alone.
2. Keep only necessary context, core decisions, real constraints, and resource-reading conditions in the body. A simple skill may consist of one file.
3. Put substantial conditional guidance in `references/` and link it from the entrypoint or a relevant resource. Do not load every reference by default. Put output materials in `assets/`.
4. Add `scripts/` only for repetitive, error-prone operations that benefit from deterministic execution. State inputs, dependencies, and failure behavior, and run the scripts to validate them.
5. Separate correctness requirements from preferences. Reserve strong constraints for real risks and state their applicability. Do not turn one incident or architecture into a universal prohibition.
6. Preserve task scope. Text suggestions do not require confirmation. Respect existing authorization for external changes; resolve missing authorization before the concrete operation without requesting approval already given.

Read [Design Patterns](references/design-patterns.md) when selecting a structure for different tasks. Read [Failure Handling](references/failure-handling.md) when designing tool failure or retry behavior.

## Validate and Deliver

- Check frontmatter, naming, relative links, tool availability, and instruction consistency. Use a host-provided validator when available, but do not equate formatting success with correct behavior.
- Use [Behavioral Validation](references/validation.md) to select representative tasks and check output improvements, false triggers, and unnecessary questions.
- Make targeted fixes and revalidate affected paths. On repeated failure, record the blocker instead of retrying indefinitely or blindly adding MUST statements.
- Report actual file locations, important behavior changes, and validation scope. Distinguish static checks, actual execution, and unverified behavior. Do not claim a universally optimal skill.
- Separate installation and publishing from source delivery; install or publish only within the requested scope.
