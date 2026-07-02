# Nav Icons

## Description

The icon set that feeds the bottom navigation. Each icon maps to one top-level destination of the Travel app and is designed to read clearly at 40px inside a [NavBar](./navbar.md) item. Delivered as a single component with a property to switch between destinations.

## Variants

| Variant | Node ID | Destination |
| --- | --- | --- |
| `Home` | `149:388` | Home / dashboard |
| `Budget` | `149:390` | Budget & expenses |
| `Trip` | `149:966` | Trips / itinerary |
| `Transport` | `158:1971` | Transport & routes |

Property name: **`Property 1`** with values `Home`, `Budget`, `Trip`, `Transport`.

## States

The icon itself is a glyph and carries no interactive state of its own — coloring is inherited from the parent NavBar item:

| Context state | Color token |
| --- | --- |
| Default (inactive nav) | `Icons/MenuNav Icon Default` → `#4f4f4f` |
| Active (selected nav) | `Icons/MenuNav Icon Active` → `#235c1f` |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Home`, `Budget`, `Trip`, `Transport` | `Home` |

## Design tokens used

- **Frame size:** 40 × 40px
- **Default fill:** `Icons/MenuNav Icon Default` `#4f4f4f` (Black 600)
- **Active fill:** `Icons/MenuNav Icon Active` `#235c1f` (Green 700)
- Stroke/fill inherits `currentColor` so a single icon serves both states

## Accessibility guidelines

- These glyphs are decorative when paired with a visible NavBar label — mark them `aria-hidden="true"` and let the label provide the accessible name.
- If ever used without a text label, each destination icon must have an `aria-label` matching its meaning.
- Do not distinguish destinations by color alone; the distinct glyph shapes carry the primary meaning.
- Ensure the active fill (Green 700) meets ≥ 3:1 non-text contrast against the bar background.
- Keep glyph line weights consistent across all four so no destination looks disabled.
