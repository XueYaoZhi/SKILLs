# Read Changes

Use the environment's terminal tool for read-only commands, with an explicit working directory. Honor a specified branch, commit, or path range. Ask when an ambiguous comparison base materially affects the result.

A typical sequence for the current workspace:

```text
git rev-parse --is-inside-work-tree
git status --short
git diff --cached --stat
git diff --cached --name-status
git diff --cached --no-ext-diff --no-textconv -- <path>
```

- If no scope is specified, prefer staged changes and state that basis. Do not mix in unstaged changes to the same file.
- If staging is empty and the user requests working-tree changes, inspect `git diff --stat` and path-specific diffs. If the user explicitly requests staged changes, report that staging is empty rather than silently changing scope.
- Untracked files are absent from ordinary diffs. Read them as needed when included in the requested scope, and identify them as untracked.
- A user description is sufficient without a repository. Ask for details only when neither source exists.

For large changes, first obtain the complete file list and statistics, then read in batches by module. Prioritize public interfaces, configuration semantics, migrations, and core logic. Generated and lock files may be summarized alongside their source changes. Do not truncate later files at a fixed count or classify changes using only the first few dozen paths.

When tool output is truncated, narrow individual reads. If time or context limits prevent full coverage, state what remains unread rather than claiming a complete review. Do not repeat secret values in commit messages.
