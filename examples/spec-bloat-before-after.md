# Example: Spec Bloat Before And After

## Before

A long project accumulates dozens of specs. Each spec is individually reasonable, but no one knows:

- which doc is current
- which doc is stale
- what the next output should be
- what counts as acceptable
- which concepts still matter

The agent keeps writing more docs to restore clarity, but the document pile itself becomes the problem.

## After

Create one small control surface:

```md
# Project Control Surface

## Read First
1. `docs/status.md` - current phase and acceptance standard
2. `README.md` - run commands
3. `src/...` - current implementation

## Current Phase
Validation

## Expected Output
Playable MVP with smoke-tested core loop.

## Acceptance Standard
Runs locally, one happy path works, known gaps are listed.

## Stale Docs
- `docs/old-contract.md` - archive only
- `docs/v1-plan.md` - replaced by current status
```

## Rule

When specs multiply faster than clarity, stop writing new specs and create a read-first control surface.
