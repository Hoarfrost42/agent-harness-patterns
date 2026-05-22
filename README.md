# Agent Harness Patterns

[中文](README.zh-CN.md) | English

Practical patterns for keeping long-running agent coding work controllable.

This repository is a field-tested toolkit, not a universal theory. It collects small rules, Codex skills, and reference templates that help reduce context bloat, stale-document drift, over-execution, and loss of human control in agent-assisted projects.

## Core Idea

Agent coding does not fail only because the model writes bad code. It often fails because the surrounding harness lets the agent:

- pull huge command output into context
- trust stale docs over current code
- keep executing when the human has lost the project map
- produce more specs instead of restoring clarity
- expose developer notes in user-facing copy
- add abstractions and concepts faster than anyone can understand them

This repo treats those as harness problems.

## What's Included

```text
snippets/     Small rules you can paste into AGENTS.md or project instructions.
skills/       Codex-style skills that package repeatable workflows.
references/   Lightweight templates and decision notes.
examples/     Concrete failure patterns and before/after examples.
```

## Recommended Starting Point

Start here if you only have five minutes:

- [5 Minute Quickstart](QUICKSTART.md)
- [Adoption Levels](references/adoption-levels.md)

Start with these three:

1. `snippets/command-output.md`
2. `skills/project-continuity-control/SKILL.md`
3. `references/control-loss-gate.md`

They solve common problems quickly: token/context blowups, stale handoffs, and agents continuing execution when the real task is to restore control.

## Install Skills

Copy a skill folder into your Codex skills directory:

```powershell
Copy-Item -Recurse .\skills\project-continuity-control "$env:USERPROFILE\.codex\skills\project-continuity-control"
```

Restart Codex after installing or renaming skills.

## Patterns

### Protect Command Output

Unknown or potentially large command output should be capped, summarized, or narrowed before it enters the model context.

### Recover Project Control

When the human cannot tell what is done, what is half-done, what should be produced, or what counts as good enough, stop execution-first work and restore the control surface.

### Prefer Current Facts

Current code, runtime behavior, scripts, tests, and production state outrank polished but stale docs.

### Keep Concepts Small

Short code is not enough. Keep the number of named concepts, managers, adapters, states, and docs low enough for the next human or agent to understand.

### User-Facing Copy Is Not Developer Notes

UI text, public pages, decks, and reports should speak to users, not future developers.

## Examples

- [Spec bloat before/after](examples/spec-bloat-before-after.md)
- [Stale doc contamination](examples/stale-doc-contamination.md)
- [Control loss gate](examples/control-loss-gate.md)

## Philosophy

Best practices are inputs, not authorities.

Borrow from strong sources, adapt to your own workflow, test in real tasks, and keep only what reduces friction or restores control.

## Status

Early personal practice repo. Use as patterns to try, not as finished doctrine.
