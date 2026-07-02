# Icon Button

## Description

A compact, circular button that carries a single icon and no text label. Used for secondary or space-constrained actions such as a floating map control, a back affordance, or a quick add. Comes in two fixed sizes so it can adapt to touch-primary surfaces (Large) or dense toolbars (Medium).

## Variants

| Variant | Node ID | Size |
| --- | --- | --- |
| `Medium Button` | `161:5019` | 40 × 40px |
| `Large Button` | `165:5164` | 45 × 45px |

Property name: **`Property 1`** with values `Medium Button` and `Large Button`.

## States

| State | Appearance |
| --- | --- |
| Default / Enabled | Brand or white surface with centered icon. |
| Hover (web) | Slight surface darken / elevation increase. |
| Pressed / Active | Deeper shade; optional scale-down feedback. |
| Focus | 2px focus ring offset from the circle. |
| Disabled | Muted surface (Black 100 `#d1d1d1`) and Black 300 (`#888888`) icon. |

> Only the resting appearance is defined in the library; interactive states follow the shared button behavior.

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Medium Button`, `Large Button` | `Medium Button` |
| Icon | instance swap | any icon | brand icon |

## Design tokens used

- **Icon:** `Icons/Brand Icon Default` `#267421` or `Icons/White Icon` `#ffffff` depending on surface
- **Shape:** circular (border-radius = 50% of size)
- **Size:** Medium 40px, Large 45px
- **Elevation:** `shadow` → drop shadow `0 4 6 rgba(0,0,0,0.09)` when floating over content
- Icon glyph sized ~24–25px, optically centered

## Accessibility guidelines

- Because there is no visible text, **an `aria-label` (or equivalent accessible name) is required** describing the action (e.g. "Add expense", "Show map").
- Large (45px) is close to but below the 44px+ recommended touch target only at Medium (40px) — pad the hit area to at least 44×44px on touch surfaces.
- Keep the icon meaning unambiguous; pair with a tooltip on pointer devices where the action may be unclear.
- Ensure icon-to-surface contrast ≥ 3:1 (non-text graphic contrast, WCAG 1.4.11).
- Provide a visible, non-color focus indicator.
