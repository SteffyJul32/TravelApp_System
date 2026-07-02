# Icons (Action Icon Set)

## Description

A small utility icon set for in-content actions and view toggles. Unlike [Nav Icons](./nav-icons.md), these are used inside buttons, toolbars, and segmented controls — for example switching a trip view between Map and List, or triggering an Add action.

## Variants

| Variant | Node ID | Meaning |
| --- | --- | --- |
| `Add` | `161:5034` | Create / add a new item |
| `Map` | `165:5141` | Switch to map view |
| `List` | `171:5541` | Switch to list view |

Property name: **`Property 1`** with values `Add`, `Map`, `List`.

## States

The glyph inherits color from its host control:

| Context | Color |
| --- | --- |
| On brand surface | `Icons/White Icon` → `#ffffff` |
| On light surface | `Icons/Brand Icon Default` → `#267421` |
| Inactive toggle | Black 300 (`#888888`) |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Add`, `Map`, `List` | `Add` |

## Design tokens used

- **Glyph size:** 25 × 25px
- **Default fill:** `Icons/Brand Icon Default` → `#267421`
- Inherits `currentColor` for placement on both brand and light surfaces

## Accessibility guidelines

- When placed inside an [Icon Button](./icon-button.md) or [Button](./button.md), the icon is decorative (`aria-hidden`) and the button label provides the accessible name.
- For view toggles (Map/List), expose the toggle state via `aria-pressed` or the Tabs pattern rather than by icon color.
- Maintain ≥ 3:1 contrast between glyph and its surface.
- Keep the visual metaphors conventional (magnifier, pin, list rows) so meaning is not learned per-app.
