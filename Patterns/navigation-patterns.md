# Navigation Patterns

How users move through the Travel app. Token references: [semantic-tokens.md](../design-tokens/semantic-tokens.md), [motion.md](../design-tokens/motion.md).

## Primary: bottom tab bar

Persistent bottom `NavBar` with four top-level destinations: **Home, Trip, Budget, Transport**.

- Container: white surface, full-width 393, `px-10 pb-10 pt-20`, items spaced `gap-10`, pinned to bottom.
- Item = stacked 40px icon + 16px label.
- **Default:** icon `Icons/MenuNav Icon Default` (`#4f4f4f`), label `#4f4f4f`, SemiBold.
- **Active:** icon `Icons/MenuNav Icon Active` (`#235c1f`), label `#000000`, Bold, plus `aria-current="page"`.
- Exactly one active item; selection shown by color **and** weight (non-color cue).
- Tab switch = cross-fade content (`motion/fast`), no slide.

## Secondary: in-page tabs

`Tab` component for switching sibling views within a screen (e.g. trip Overview/Itinerary/Budget).

- Active: brand text + `Border/Tab/Tab Active` underline, Bold. Default: muted text + neutral underline, Medium.
- Use the ARIA tablist pattern with arrow-key support.

## Contextual navigation

- **Back:** directional chevron/arrow icon (top-left); pop transition slides out to the right (`motion/base`).
- **"See all" / drill-in:** trailing text button on section headers → pushes a detail/list screen (slide-in from right, `motion/slow`).
- **Card / list-row tap:** whole card is one target → navigates to detail.
- **Map ↔ List toggle:** `Icons` Map/List variants switch representation of the same data (use `aria-pressed`).

## View transitions

| Action | Motion |
|--------|--------|
| Push (forward) | Slide-in from right, `motion/slow`, ease-decelerate |
| Pop (back) | Slide-out right, `motion/base`, ease-accelerate |
| Tab switch | Cross-fade, `motion/fast` |
| Bottom sheet / modal | Slide-up, `motion/slow`; scrim fade `motion/base` |

## Responsive

Bottom tab bar → left sidebar at `bp-desktop` (see [breakpoints.md](../design-tokens/breakpoints.md)).

## Rules

Four bottom-nav destinations, always visible, one active. Use in-page `Tab` for sub-views, never a second bottom bar. Every nav target ≥44px, keyboard-reachable, with a text label. Signal the current location with `aria-current`/`aria-selected` + weight, not color alone.
