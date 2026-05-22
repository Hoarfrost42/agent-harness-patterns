# 5 Minute Quickstart

Use this repo as a small toolbox. Do not install everything first.

## Do I Need This?

You probably need it if agent coding work often has one of these symptoms:

| Symptom | Start with |
| --- | --- |
| Commands dump huge logs, diffs, or JSON into context | `snippets/command-output.md` |
| The agent trusts old docs over current code | `skills/project-continuity-control/SKILL.md` |
| The project keeps moving, but you cannot tell what is done | `references/control-loss-gate.md` |
| Specs and handoffs multiply faster than clarity | `examples/spec-bloat-before-after.md` |
| UI copy sounds like developer notes | `snippets/user-visible-copy.md` |
| Code works, but concepts keep piling up | `skills/straight-line-code-discipline/SKILL.md` |

Skip this repo if your agent tasks are mostly short, isolated, and easy to verify.

## First Paste

Paste this into your project instructions or `AGENTS.md` first:

```md
## Command Output

- Protect context usage. Limit unknown or potentially large command output first.
- Prefer narrow queries: `rg pattern path -n -m 80`, `git diff --stat`, `git diff --name-only`, `Get-Content path -TotalCount 200`, `Get-Content path -Tail 200`.
- For logs, build output, long JSON, database exports, full diffs, and large files, start with summaries, matches, line limits, or filename lists.
- Read full output only when necessary for the current decision.
```

## First Control Check

When the work starts feeling out of control, ask the agent for this instead of another implementation batch:

```md
Stop execution-first work. Build a compact control surface:

1. What is done?
2. What is half-done?
3. What is unverified?
4. What is obsolete or stale?
5. What is the current phase?
6. What output should this phase produce?
7. What counts as acceptable?
8. What are the next 1-3 decisions?
```

## Install One Skill

If you use Codex skills, start with one:

```powershell
Copy-Item -Recurse .\skills\project-continuity-control "$env:USERPROFILE\.codex\skills\project-continuity-control"
```

Restart Codex after installing or renaming skills.

## Keep It Small

Add one rule, run one real task, then decide whether it helped.

If a rule does not reduce confusion, context bloat, stale-doc drift, or rework, remove it.
