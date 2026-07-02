# Active Date

## Description

A compact date cell used in horizontal date pickers and itinerary day-strips. Each cell stacks a weekday abbreviation over a day number. The Active variant highlights the currently selected day so users can scrub through trip days quickly.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Active` | `175:7376` | Selected day — brand-filled pill. |
| `Default` | `175:7378` | Unselected day — plain text on transparent background. |

Property name: **`Property 1`** with values `Active` and `Default`.

## States

| State | Appearance |
| --- | --- |
| Default | Neutral text (Black 800 `#3d3d3d`), no fill. |
| Active | Brand fill (Green 600 `#267421`) with white text. |
| Hover (web) | Light brand tint (`#e2f8e0`) behind the cell. |
| Focus | Focus ring around the cell. |
| Disabled | Muted Black 300 (`#888888`) text for out-of-range days. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Active`, `Default` | `Default` |
| Weekday | text | Mon–Sun | — |
| Day number | text | 1–31 | — |

## Design tokens used

- **Active surface:** `Surface/Background/Background Active` → `#267421`
- **Active text:** `Text/Button Text/White text` → `#ffffff`
- **Default text:** `Text/Text/Subtitle` → `#3d3d3d`
- **Typography:** DM Sans — weekday `11pt Medium Caption`, day number `16pt SemiBold/Bold Title`
- **Cell size:** ~49 × 59px
- **Corner radius:** `radius-md` 8px

## Accessibility guidelines

- Build on the date-picker / grid pattern; mark the selected day with `aria-selected="true"` (or `aria-current="date"`), not color alone.
- Support keyboard navigation across days (arrow keys) with a visible focus indicator distinct from the selected fill.
- Announce the full date on focus (e.g. "Tuesday, 4 August") rather than just the number.
- White-on-Green 600 for the active cell meets AA contrast; verify the default Black 800 text also passes at the small weekday size.
- Ensure each cell is at least a 44px tap target on touch.
