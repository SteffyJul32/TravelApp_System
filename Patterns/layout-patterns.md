# Layout Patterns

Reusable screen-composition patterns observed across the iPhone 16 (393×852) screens. Reuse these before inventing new layouts. Token references: [spacing.md](../design-tokens/spacing.md), [semantic-tokens.md](../design-tokens/semantic-tokens.md).

## Screen scaffold

```
Status bar (iOS)                → top, system
Content column   w-343, left-25, top-65, gap-15   → vertical Auto Layout
Bottom nav bar   w-393, fixed bottom (top-751)     → white, px-10 pb-10
```

- App canvas: `#f0f2f0` (tokenize as `Surface/App`).
- Horizontal screen padding: **25px** (content column 343px, centered-left).
- Sections stack vertically with **gap-15**; groups inside a section use **gap-10**; text blocks use **gap-2 → gap-5**.

## Header pattern

Row, `justify-between`, `items-center`: greeting/title (24pt Bold) on the left, circular avatar (35px, Green 800 fill, initial in 14pt Bold White) on the right.

## Section header pattern

Row, `justify-between`: section title (16pt Bold) + optional trailing [Text Button](../design-tokens/icons.md) ("See all" + 8px chevron). Followed by the section's content with `gap-5`/`gap-10`.

## Content blocks

- **Hero/banner:** full-width (343) `Banner template`, `radius-lg`, `shadow`, image top + white caption bar (`px-15 py-10`); optional pager dots below.
- **Featured card:** `Trip thumbnail` (343 wide) — image header (`radius-t-lg`) + white body with title, date row (icon+meta), avatar cluster.
- **Horizontal media row:** 130×130 image tiles, `gap-10`, label bottom-left over a dark gradient scrim; wraps to a grid at ≥ tablet.
- **List:** stacked `Fill` rows, full-width, list semantics.

## Card anatomy

Image area (`radius-t-lg`) → white content area (`bg-white`, `px-15 py-10`, `radius-b-lg`) → shadow `shadow`. Title `Text/Text/Title`, meta `Text/Text/Subtitle`.

## Rules

- One content column, 25px side padding, vertical Auto Layout — don't free-position.
- Reuse the gap ladder (2/5/10/15); 15 between sections only.
- Cards always = white body + `radius-lg` + `shadow`.
- Keep the bottom nav persistent and out of the scrolling content.
