# Example: Control Loss Gate

## Before

A long-running project has working code, several specs, and many partially finished ideas.

The agent keeps proposing the next implementation batch:

```text
Next I will add the remaining screens, wire the state manager, update the docs, and run tests.
```

But the human's real problem is different:

- they cannot tell which pieces are finished
- they cannot tell which docs are current
- they cannot tell what this phase should output
- they cannot judge whether the direction is still worth continuing

More execution makes the project feel less controllable.

## Trigger

Use the control-loss gate when the user says things like:

```text
Stop for a moment.
I feel like this is getting out of control.
I do not know what we are producing anymore.
I do not know whether this is still worth doing.
```

## After

The agent stops execution-first work and produces a compact control surface:

```md
# Project Control Surface

## Current Phase
MVP validation.

## Done
- Local app starts.
- Main workflow has one happy path.

## Half-Done
- Secondary states exist but are not verified.
- Visual polish is inconsistent.

## Unverified
- Error paths.
- Production build.
- User-facing copy.

## Stale Or Suspect
- `docs/v1-plan.md`: replaced by current implementation.
- `docs/backend-contract-old.md`: conflicts with current routes.

## Expected Output
A demoable MVP with one reliable path and known gaps.

## Acceptance Standard
Runs locally, happy path works, build passes, gaps are listed.

## Next Decisions
1. Polish the existing path or expand scope?
2. Delete stale docs or archive them?
3. Add tests now or after the demo pass?
```

## Rule

When the human loses the project map, clarity is the deliverable.
