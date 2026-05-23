# Skills Index Template

Use this as a lightweight routing reference. It does not change skill discovery.

## Agent Entry Point

This file is for the agent to read before stacking skills or creating new ones. Humans should not need to decide whether a task needs a snippet, reference, or skill. The agent should route to the smallest useful layer.

Use this file when:

- a task may match multiple skills
- a new skill may duplicate an existing one
- a project feels out of control and execution may be premature
- a user asks which skill should handle a task

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
