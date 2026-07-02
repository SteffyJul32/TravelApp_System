# Shadow & Elevation Tokens

Two elevation levels are defined as effect variables. Both are soft, low-opacity black drop shadows — a flat, subtle elevation system.

| Token | CSS Value | Usage |
|-------|-----------|-------|
| shadow-xs (`Box Shadow/shadow-xs`) | `0 1px 2px rgba(0,0,0,0.10)` | Inputs, resting flat controls |
| shadow (`shadow`) | `0 4px 6px rgba(0,0,0,0.09)` | Raised: cards, banners, thumbnails, floating icon buttons, snackbar, map pins |

> Figma effect defs: shadow-xs = DROP_SHADOW `#0000001A` offset(0,1) radius 2; shadow = DROP_SHADOW `#00000017` offset(0,4) radius 6. Some exported frames render `0 4px 3px rgba(0,0,0,0.09)` — treat the variable (`radius 6`) as canonical.

## Elevation scale

| Level | Token | Applied to |
|-------|-------|-----------|
| 0 | none | Screen background, inline text, list dividers |
| 1 | shadow-xs | Text inputs, resting secondary controls |
| 2 | shadow | Cards, banners, snackbar, FAB / icon button, active map pin |

## Rules

- Only two elevation steps exist — do not invent level 3+. Use overlap/scale or brand tint for extra emphasis instead.
- Floating and content-raised elements share the same `shadow`; keep it consistent so hierarchy reads by position, not shadow depth.
- Never hardcode shadow values; reference `shadow-xs` / `shadow`.
- Keep shadow color black at ≤10% opacity to match the flat aesthetic.
