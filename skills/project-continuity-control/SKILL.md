---
name: project-continuity-control
description: Preserve project continuity and control context bloat across agent windows. Use for continuing old work, reading repo truth sources and Git diff, summarizing project state, writing layered handoffs, building read-first indexes, preventing handoff/SPEC/document sprawl, detecting stale-doc contamination, and clarifying what future agents can actually inherit.
---

# Project Continuity Control

## Purpose

Build continuity from the repository itself, not from chat memory alone. The output should let a future agent regain project control without rediscovering the project from scratch.

## Recovery Order

1. Read project instructions, README, task docs, coordination docs, and existing handoff files.
2. Inspect real repo state: branch, `git status --short`, recent commits, and targeted diff.
3. Find active truth sources: specs, task boards, architecture docs, schemas, test commands, deployment notes, or handoff indexes.
4. Compare memory against repo facts. Prefer live repo files when they disagree.
5. Continue work, write a handoff, or produce a read-first/control index according to the latest user intent.

## Current Fact Priority

```text
current code > current production/runtime behavior > README or root handoff entry > runbook > current docs > historical research > archive > old contracts
```

Polished old docs are suspect until checked against current code or runtime behavior.

## Stale-Doc Contamination Check

Before writing a handoff, read-first index, or continuity report, search for:

- deleted, renamed, or disabled routes
- old project names
- old deployment commands
- old API contracts
- feature states that contradict current code
- docs that describe former architecture as current behavior

Classify stale material as historical reference, downgraded/stale, rewritten into current truth, or delete candidate.

## Handoff Object Boundaries

State what a future agent can inherit.

Usually inheritable:

- repository files, commits, issues, PRs
- production servers and databases when accessible
- repo-local runbooks and durable architecture docs

Not safely inherited by default:

- personal machine state
- local automations
- private repos outside the project
- chat memory
- temporary logs
- uncommitted scratch files unless listed

## Layered Handoff

Do not write the longest possible handoff by default.

Use three layers:

1. Quick recovery prompt: 10-20 lines for a known next task.
2. Fact index: paths, branch, dirty files, truth sources, validation commands, current phase, and open risks.
3. Full archive: detailed history and evidence only when loss of detail would create real risk.

## Spec Bloat Control

When specs multiply faster than clarity:

1. Identify current truth sources.
2. Mark stale or superseded docs.
3. Add a read-first order.
4. Avoid duplicating one decision across many docs.

If the human has lost project control, produce a project map before writing another full handoff.
