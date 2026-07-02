# Accessibility Standards

Inferred from the design; target **WCAG 2.1 AA**. Includes concrete contrast findings from the token set and flags for gaps to close.

## Minimum touch targets

- Standard: **44 × 44px** (WCAG 2.5.5 / iOS HIG). 
- At risk in current design: Medium icon button (40px), 25px inline icons, bottom-nav glyph (40px) — **pad hit areas to ≥44px** even when the visual is smaller.
- Primary Button (48px height) and date cells (~49×59) already pass.

## Text sizes

- Smallest UI text is **10px** (time) and **11px** (captions) — below the 12px comfort floor. Restrict 10–11px to non-essential meta; never use for actionable or critical content. Body defaults to Inter 14–16px.

## Contrast findings (on white `#ffffff`)

| Foreground | Ratio | Verdict |
|-----------|-------|---------|
| Black 950 `#000000` (Title) | 21:1 | ✅ AAA |
| Black 800 `#3d3d3d` (Subtitle/input) | 10.6:1 | ✅ AAA |
| Black 600 `#4f4f4f` (nav default) | 8.1:1 | ✅ AAA |
| Green 700 `#235c1f` (brand text/button) | 7.9:1 | ✅ AAA |
| Green 600 `#267421` (icons) | 5.9:1 | ✅ AA |
| Black 300 `#888888` (placeholder/disabled/default btn text) | 3.5:1 | ⚠️ Fails AA for normal text; OK ≥18px / UI only |
| Border `#b0b0b0` on white | 2.0:1 | ⚠️ Fails 1.4.11 (3:1) for essential UI borders |
| White on Green 700 / 600 | 7.9 / 5.9:1 | ✅ AA+ |

**Actions:** don't use Black 300 for essential body text or the sole label of a control; darken default input/tab borders (`#b0b0b0`) toward `#5d5d5d` (already the active-border token) or add a 3:1-compliant outline.

## Focus states

- **Not defined in the file.** Add a visible focus indicator to every interactive element: 2px ring, Green 600 `#267421`, ≥2px offset, with ≥3:1 contrast against adjacent colors. Never remove focus outlines without an equivalent replacement.

## Disabled states

- Represented by surface `Background Default #d1d1d1` + text `#888888`. Disabled contrast is intentionally low — always pair with `disabled`/`aria-disabled` so state isn't conveyed by color alone.

## Missing considerations (close these)

- No **error/validation** color or pattern → add Status/Error and `aria-invalid` + text messaging (see [colors.md](./colors.md)).
- No **focus** styling defined (above).
- **Placeholder-as-label** risk in inputs → always keep a persistent visible `<label>`.
- No **reduced-motion** guidance → see [motion.md](./motion.md).
- Icon-only controls (icon button, map pins) need **`aria-label`s**.
- Selection/active states must carry a **non-color cue** (weight, checkmark, `aria-current`/`aria-selected`), not color only.

## Rules

Meet AA (4.5:1 text, 3:1 UI/large). Every control: keyboard-operable, visibly focusable, ≥44px, with a text accessible name. Never signal state by color alone.
