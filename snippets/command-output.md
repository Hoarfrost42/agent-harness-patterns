# Command Output Context Protection

Protect context usage. Any command with unknown or potentially large output should be narrowed before it is read into the agent context.

## Rule

Prefer targeted queries over full dumps:

```powershell
rg "pattern" path -n -m 80
git diff --stat
git diff --name-only
Get-Content path -TotalCount 200
Get-Content path -Tail 200
```

For logs, build output, long JSON, database exports, full diffs, and large files:

1. Start with names, stats, counts, or small samples.
2. Search for the relevant pattern or time window.
3. Read the full output only when it is necessary for the current decision.

## Why

Large command output can pollute the working context, raise token usage, and make later reasoning worse. The goal is not to hide evidence, but to pull in the smallest useful evidence first.

## AGENTS.md Snippet

```md
## Command Output

- Protect context usage. Limit unknown or potentially large command output first.
- Prefer narrow queries: `rg pattern path -n -m 80`, `git diff --stat`, `git diff --name-only`, `Get-Content path -TotalCount 200`, `Get-Content path -Tail 200`.
- For logs, build output, long JSON, database exports, full diffs, and large files, start with summaries, matches, line limits, or filename lists.
- Read full output only when necessary for the current decision.
```
