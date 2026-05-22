# Context Hygiene

Long-running agent work needs context hygiene, not just better prompts.

## Rules

- Prefer current truth sources over old summaries.
- Keep a read-first index for large projects.
- Split handoffs into layers: quick recovery prompt, fact index, full archive.
- Mark stale docs clearly or move them out of the active path.
- Do not let old contracts, old site reviews, or old quickstarts look like current truth.
- Avoid adding new specs when updating an existing living document is enough.

## Read-First Index Shape

```md
# Read First

## Current Truth Sources

1. `README.md` - project entry and run commands
2. `docs/project/status.md` - current phase and open risks
3. `src/...` - current implementation

## Stale Or Historical

- `docs/archive/old-contract.md` - old API contract, no longer authoritative
- `docs/research/site-review.md` - historical research only
```
