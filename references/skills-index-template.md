# Skills Index Template

Use this as a lightweight routing reference. It does not change skill discovery.

## Routing Rules

- Use ordinary reasoning when no skill is needed.
- Choose the smallest useful skill set.
- Prefer project-specific rules before broad domain skills.
- Classify overlapping skills by role: primary method, guardrail, execution pass, verification pass.
- Treat official or vendor skills conservatively; prefer local routing rules over editing vendor internals.

## Inventory

| Skill | Purpose | Trigger | Status |
| --- | --- | --- | --- |
| `skill-router` | Select the smallest useful skill set | Skill conflict or routing ambiguity | active |
| `project-continuity-control` | Recover current truth and prevent stale docs | Handoff, continuation, stale docs, read-first index | active |
| `straight-line-code-discipline` | Keep code and concepts clear | Writing, refactoring, bloated diffs | active |
| `no-visible-meta-copy` | Remove developer-facing visible copy | UI copy, public pages, decks, reports | optional |

## Notes

Keep this file short. Move project-specific overrides into a separate reference.
