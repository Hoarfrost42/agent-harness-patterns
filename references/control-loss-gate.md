# Control-Loss Gate

Use this when the human's main problem is not implementation, but loss of project control.

## Trigger Signals

- "I don't know where the project stands."
- "I don't know what should be produced next."
- "I don't know what counts as good enough."
- "There are too many specs, tasks, concepts, or diffs."
- "This works, but I don't know whether it is worth continuing."
- "Stop. Let's discuss."

## Response

Do not continue execution-first work. Produce a compact control surface:

1. Progress map: done, half-done, unverified, undecided, obsolete.
2. Current phase.
3. Expected output for this phase.
4. Acceptance standard.
5. Active concepts and possible duplicates.
6. Next 1-3 decisions.

## Severity Rubric

Use the smallest intervention that restores control.

| Severity | Signals | Response |
| --- | --- | --- |
| Mild drift | The next step is fuzzy, but the project map is still mostly intact. | Continue work, but first name the current phase, next output, and acceptance standard. |
| Moderate control loss | The human cannot tell what is done, half-done, unverified, or worth continuing. | Pause scope expansion and produce the compact control surface before more implementation. |
| Severe control loss | Current docs conflict, concepts have multiplied, old work contaminates new work, or the human cannot trust the project map. | Freeze implementation. Rebuild truth sources, stale-doc status, concept map, and next decisions before executing. |

## Delivery Mode Exception

If the user is clearly in a delivery deadline or production push, continue toward the deliverable, but record complexity debt and recovery points for the maintenance phase.
