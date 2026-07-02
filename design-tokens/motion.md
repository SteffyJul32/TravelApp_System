# Motion Tokens

The Figma file is **static** — no prototype flows, Smart Animate, or transition specs are defined. The following are **recommended defaults** to establish a consistent motion language for a mobile-first travel app. Adopt and encode these as tokens.

## Duration

| Token | Value | Usage |
|-------|-------|-------|
| motion/instant | 100ms | Hover/press color feedback |
| motion/fast | 150ms | Small state changes (tab, toggle, checkbox) |
| motion/base | 250ms | Standard — snackbar in/out, dropdown, sheet content |
| motion/slow | 350ms | Page / screen transitions, bottom-sheet open |

## Easing

| Token | Curve | Usage |
|-------|-------|-------|
| ease-standard | `cubic-bezier(0.2, 0, 0, 1)` | Most enter/exit and movement |
| ease-decelerate | `cubic-bezier(0, 0, 0, 1)` | Elements entering the screen |
| ease-accelerate | `cubic-bezier(0.3, 0, 1, 1)` | Elements leaving the screen |
| ease-emphasized | `cubic-bezier(0.2, 0, 0, 1)` | Hero / large surface moves |

## Principles

- **Purposeful:** motion clarifies hierarchy and continuity (where a screen came from), never decorative.
- **Fast & subtle:** mobile taps should feel instant; keep most transitions ≤ 250ms.
- **Consistent direction:** forward navigation slides in from the right / up; back reverses it.
- **Respect users:** honor `prefers-reduced-motion` — swap slides/scales for simple fades.

## Navigation transitions

| Transition | Motion |
|-----------|--------|
| Push (forward) | Slide-in from right, `motion/slow` + ease-decelerate |
| Pop (back) | Slide-out to right, `motion/base` + ease-accelerate |
| Tab switch (bottom nav) | Cross-fade content, `motion/fast`; no slide |
| Bottom sheet / modal | Slide-up from bottom, `motion/slow`; scrim fades `motion/base` |
| Snackbar | Slide-up + fade in `motion/base`, auto-dismiss fade-out |
| Map pin select | Scale 1→1.1 + elevation, `motion/fast` |

## Rules

Use only the four durations and named easings above. Never animate layout-critical properties in ways that block interaction. Provide a reduced-motion fallback for every non-trivial transition.
