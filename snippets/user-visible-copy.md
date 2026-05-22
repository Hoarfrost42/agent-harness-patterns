# User-Facing Copy Boundary

Visible product copy should speak to users, not future developers.

## Rule

Text in pages, product UI, public docs, decks, reports, buttons, cards, empty states, tooltips, toasts, and modals is user-facing by default.

Do not write it as:

- implementation notes
- future TODOs
- technical field explanations
- data-chain maintenance notes
- internal scope disclaimers
- developer-facing placeholder text

## Replace This

```text
This section later displays the current aggregation result. The field is used to maintain this link.
```

## With This

```text
Data is grouped by source, conversion, search activity, and content quality.
```

## AGENTS.md Snippet

```md
## User-Facing Copy

- Text written into pages, product UI, public docs, decks, reports, buttons, cards, empty states, tooltips, toasts, and modals is user-facing by default.
- User-facing copy should describe value, status, action, result, or limitation for the end user.
- Do not expose developer notes, future TODOs, technical chains, field-maintenance wording, internal scope notes, or placeholder explanations.
- Put technical explanation in comments, handoffs, specs, README files, PR notes, or internal annotations instead.
```
