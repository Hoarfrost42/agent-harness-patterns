---
name: skill-router
description: Route tasks to the minimal useful set of local skills. Use when skill choice is ambiguous, multiple skills overlap, a duplicate skill may be created, or a complex project feels out of control and execution skills may be the wrong next step.
---

# Skill Router

## Purpose

Choose skills deliberately. The goal is not to use more skills; the goal is to use the smallest set that improves the work.

## Routing Rules

1. If ordinary reasoning is enough, use no skill.
2. If a project-specific skill clearly applies, use it before broad domain skills.
3. For overlapping skills, classify roles before choosing:
   - primary method
   - guardrail
   - execution pass
   - verification pass
4. Prefer one primary method. Add other skills only when their roles are distinct.
5. Add review skills only when the user asks for review or the result needs validation.
6. Add tool/media skills only when the output requires that tool or file type.
7. Treat official or vendor skills conservatively; prefer local routing rules over editing their internals.

## Control-Loss Gate

Before selecting execution skills, check whether the human's main pain is loss of project control.

Trigger when the user says or implies:

- the project is out of control
- they cannot tell what is done or unverified
- they do not know what should be produced next
- they do not know what counts as good enough
- specs, concepts, or tasks are accumulating faster than clarity
- they want to pause and discuss whether to continue

When triggered, prefer project map recovery, phase/output clarification, concept reduction, and review before implementation.

## Output Pattern

When routing matters, explain briefly:

```md
Use:
- `skill-a`: primary method
- `skill-b`: guardrail

Do not use:
- `skill-c`: overlaps and would add noise
```
