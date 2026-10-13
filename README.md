# Agent Skills — English Edition

English translations of the three v2 skills in this project. Each skill retains its original name, version (`2.0.0`), resource layout, and behavioral requirements.

## Available Skills

| Skill | Purpose | Entrypoint |
| --- | --- | --- |
| `high-quality-skill-creation` | Create, review, and improve Agent Skills with task-appropriate instructions, supporting resources, and validation | [SKILL.md](high-quality-skill-creation/SKILL.md) |
| `generate-conventional-commit` | Generate accurate Conventional Commits messages from change descriptions or a specified Git diff | [SKILL.md](generate-conventional-commit/SKILL.md) |
| `java-best-practice-skill` | Support Java implementation, review, and refactoring through evidence-based correctness, concurrency, design, and performance checks | [SKILL.md](java-best-practice-skill/SKILL.md) |

## Directory Structure

```text
eng_ver/
├── README.md
├── high-quality-skill-creation/
│   ├── SKILL.md
│   └── references/
│       ├── design-patterns.md
│       ├── failure-handling.md
│       └── validation.md
├── generate-conventional-commit/
│   ├── SKILL.md
│   └── references/
│       ├── message-rules.md
│       └── read-diff.md
└── java-best-practice-skill/
    ├── SKILL.md
    └── references/
        ├── core.md
        ├── concurrency.md
        ├── design.md
        ├── performance.md
        └── review.md
```

## Installation and Use

1. Select the skill you need and copy its entire directory, including `references/`, to a skill location supported by your host application.
2. Follow the host's discovery or reload procedure. Creating these files alone does not install or activate them.
3. Invoke the skill using the mechanism supported by your host. In hosts that support explicit `$skill-name` invocation, examples include:

```text
Use $high-quality-skill-creation to improve the skill in this directory.

Use $generate-conventional-commit to write a message for my staged changes.

Use $java-best-practice-skill to review this Java service for concurrency defects.
```

The English and Chinese editions share the same skill identifiers. Install one edition of each skill in a given discovery scope to avoid duplicate names. English instructions do not require English task outputs: user and project language requirements still apply.

## Behavior and Boundaries

- **Skill creation:** scales structure and checks to the task; does not assume fixed tool names, installation paths, or mandatory confirmation for text suggestions.
- **Commit messages:** permits read-only Git inspection, preserves the selected diff scope, and does not stage, commit, reset, or push.
- **Java work:** reads references as needed, preserves project architecture and target JDK compatibility, and distinguishes demonstrated defects from design preferences.

Each entrypoint specifies when to read supporting documents. References are not intended to be loaded in full for every request.

## Validation Status

The 13 skill documents were checked for:

- Valid entrypoint frontmatter using the local `skill-creator` validator.
- Existing local reference targets and reachability from each entrypoint.
- Closed Markdown code fences.
- Absence of Chinese ideographs in the translated skill documents.

These are static checks, not proof of translation equivalence or successful task execution. No independent behavioral evaluation or Java project compilation was performed for this edition. 

## Maintenance

Keep entrypoints concise and place substantial conditional guidance in references. When changing behavior, review both language editions, verify local links, and test representative affected tasks. Report actual verification results separately from untested expectations.
