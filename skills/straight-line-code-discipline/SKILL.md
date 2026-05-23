---
name: straight-line-code-discipline
description: Keep implementation code short, clear, behavior-equivalent, concept-light, and architecturally sustainable. Use when writing code, adding features, refactoring, reviewing bloated diffs, reducing concept sprawl, or deciding whether managers, adapters, registries, configs, boundaries, defensive checks, or extension points are justified.
---

# Straight-Line Code Discipline

## Purpose

Write code that future humans and agents can still understand, change, and delete. Bias toward the shortest clear implementation that preserves behavior.

Inspired by simplicity and surgical-change principles in Karpathy-style agent coding guidance, then adapted for long iterative projects where patches and borrowed implementations can accumulate into confusing architecture.

## Priority Order

1. Preserve equivalent behavior.
2. Make data flow and intent clear.
3. Keep the concept count low enough for the project to remain controllable.
4. Make implementation as short as possible without harming 1-3.
5. Preserve clear architecture and ownership boundaries.
6. Add robustness only at real boundaries.
7. Add extensibility only for known changes.

## Straight-Line Rule

Prefer direct value flow:

```text
input -> named real concept -> output
```

Avoid alias chains:

```text
a -> d -> wrapper -> manager -> f -> output
```

Middle layers are allowed only when they do real work:

- name a domain concept
- isolate an external boundary
- remove meaningful duplication
- make validation or testing easier
- separate stable core logic from volatile edge logic

## Concept Budget

Before adding a module, class, manager, resolver, state bucket, document type, workflow phase, token, or named abstraction, ask:

1. Is this a real user/domain/runtime concept or external boundary?
2. Does it own behavior or data that cannot belong to an existing concept?
3. Would merging it into an existing concept make the system clearer?
4. Is it fixing a real problem, or patching confusion from a previous abstraction?
5. Can it be a field, state value, pure function, or local mapping?

For complex work, keep each implementation round to 3-5 active core concepts when possible. If more are required, pause and write a concept map before coding.

## Architecture Rules

Do not flatten real boundaries just to reduce line count. Keep boundaries when they protect:

- domain logic vs UI/presentation
- runtime/core state vs adapters
- pure computation vs side effects
- external boundary handling vs internal trusted flow
- durable data model vs temporary view state
- project orchestration vs one feature implementation

## Allowed Abstraction Examples

Keep an abstraction when removing it would make the system less clear or less safe:

- A stable domain object used by several features should stay named instead of becoming repeated loose fields.
- A third-party API, database, file system, or model call should keep an adapter boundary so side effects stay isolated.
- A complex state machine should keep explicit states and transitions rather than hiding them in scattered booleans.
- A pure calculation should stay separate from UI or I/O code when that makes behavior easy to test.
- A durable data contract should stay separate from temporary view state or formatting logic.

## Review Checklist

- Is there one clear path from input to output?
- Did each new concept earn its name?
- Did this keep the active concept set small enough to understand?
- Did this add a manager, adapter, registry, or config just to look architectural?
- Are defensive checks placed at real boundaries?
- Can the next agent understand where to make the next change?
- Did validation prove behavior equivalence?
