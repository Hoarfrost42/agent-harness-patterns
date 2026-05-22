---
name: no-visible-meta-copy
description: Remove visible meta copy, self-explanation, defensive framing, developer-facing placeholder/TODO language, technical chain explanations, field-maintenance wording, and reading instructions from polished user-facing text such as slides, websites, UI copy, reports, articles, scripts, and documents.
---

# No Visible Meta Copy

## Core Rule

Audience-facing text must say the thing, not explain how the thing is being presented.

If text appears in product UI, public pages, decks, report bodies, cards, buttons, tooltips, toasts, modals, empty states, or help text, treat it as user-facing by default.

## Remove Or Rewrite

Remove visible copy that exposes:

- design intent
- page function
- reading instructions
- defensive framing
- process commentary
- developer TODOs
- internal data-chain explanations
- technical field-maintenance wording
- placeholder or future-development notes

## Audience Test

Before shipping user-facing copy, ask:

1. Is the reader an end user?
2. Does this sentence describe user value, status, action, result, or limitation?
3. Would it make sense without implementation context?
4. If it exists only for developers, can it move to comments, specs, README, PR notes, or handoff docs?

## Example

Bad:

```text
This area later displays the current aggregation result. The field is used to maintain this link.
```

Good:

```text
Data is grouped by source, conversion, search activity, and content quality.
```
