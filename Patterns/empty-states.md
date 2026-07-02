# Empty State Patterns

The home screen hints at empty/starter states ("Schedule a trip now" banner, first-trip prompts). No dedicated zero-data screens are drawn, so this documents the **recommended** pattern built from existing components and tokens.

## Anatomy

A centered block within the standard content column:

```
[ Illustration / Image ]     ~130px, muted (Black 50 placeholder ok)
Title        16–18pt Bold, Text/Text/Title
Body         14pt Regular (Inter), Text/Text/Subtitle, ≤2 lines
[ Primary Button ]           Green 700, full-width or hugged
[ Text Button ]  (optional secondary)
```

- Vertical stack, `gap-10` internal, centered horizontally.
- Sits inside the 25px-padded column; vertically centered in available space.

## Variations

| Context | Title | Primary action |
|---------|-------|----------------|
| No trips | "No trips yet" | `Button` "Schedule a trip" |
| No expenses (Budget) | "Nothing tracked yet" | `Button` "Add expense" |
| Empty search / list | "No results" | `Text Button` "Clear filters" |
| No saved places | "Save places to see them here" | `Button` "Explore" |
| Error / offline | "Something went wrong" | `Button` "Retry" |

## Token usage

- Title: `Text/Text/Title`, 16–18pt Bold DM Sans.
- Body: `Text/Text/Subtitle` (`#3d3d3d`), Inter 14/20 — avoid `#888888` for essential copy ([accessibility.md](../design-tokens/accessibility.md)).
- Illustration placeholder: Black 50 `#e7e7e7`, `radius-lg`.
- Primary action: `Button` (see [semantic-tokens.md](../design-tokens/semantic-tokens.md#primary-button)).

## Rules

- Every empty state = illustration + title + one-line explanation + **one primary action** to resolve it. Never a dead end.
- Reuse `Button` / `Text Button`; don't invent bespoke CTAs.
- Distinguish *empty* (no data yet, encouraging) from *error* (something failed, offer Retry) in tone.
- Keep copy short, action-oriented, and positive. Ensure the action target ≥44px and focusable.
