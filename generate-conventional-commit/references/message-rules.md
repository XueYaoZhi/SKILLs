# Format and Classification

Source: [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/).

Use `type(scope)!: description`, with optional scope and `!`. Separate the body and footers with blank lines.

- feat represents new functionality; fix represents a bug fix.
- docs, style, refactor, perf, test, build, ci, chore, and revert are common conventions, not an exhaustive enumeration mandated by the specification. Prefer categories supported by the project.
- Mark confirmed incompatible changes with `!` or `BREAKING CHANGE:`. The body may explain migration impact. Deleted files alone do not prove a breaking change.
- Lowercase types, a 72-character subject, kebab-case scopes, and body line widths are optional project conventions, not universal requirements.
- If an explicit user value conflicts with project checks, explain the conflict and offer a compatible candidate. Do not silently change the request or falsely claim validation passed.

```text
fix(auth): reject expired tokens when accessing protected endpoints
```

```text
feat(api)!: change the user role field to an array

BREAKING CHANGE: role changes from a string to an array; callers must update their parsing logic.
```

Use the second example only when evidence confirms that incompatible change. Issue footers must contain real identifiers supplied by the user or repository.
