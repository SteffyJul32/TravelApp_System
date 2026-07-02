# Location Icon

## Description

A category icon set used to classify points of interest on maps, itinerary lists, and location cards. Each variant represents a place type so users can scan and distinguish stops at a glance (airports, shops, food, landmarks). Typically nested inside a [Location](./location.md) map pin or a [Fill](./fill.md) list row.

## Variants

| Variant | Node ID | Category |
| --- | --- | --- |
| `Airport` | `169:5254` | Airports / air travel |
| `Shop` | `169:5256` | Shopping / retail |
| `Food` | `171:5265` | Restaurants / dining |
| `Landmark` | `173:6731` | Sights / attractions |

Property name: **`Property 1`** with values `Airport`, `Shop`, `Food`, `Landmark`.

## States

The glyph is presentational; color is set by its container:

| Context | Color |
| --- | --- |
| On brand pin | `Icons/White Icon` → `#ffffff` |
| On light chip | `Icons/Brand Icon Default` → `#267421` |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Airport`, `Shop`, `Food`, `Landmark` | `Airport` |

## Design tokens used

- **Glyph size:** 25 × 25px
- **Fill:** `Icons/White Icon` `#ffffff` (on brand pin) or `Icons/Brand Icon Default` `#267421` (on light surface)
- Inherits `currentColor`

## Accessibility guidelines

- Category is meaningful information, so when the icon is the only indicator of place type it must carry a text alternative (`aria-label`, e.g. "Restaurant").
- When a visible category label accompanies the icon, mark the glyph `aria-hidden="true"`.
- Do not encode category by color alone — the distinct glyph shapes are the primary differentiator.
- Ensure ≥ 3:1 contrast against the pin/chip background (white glyph on Green 600 passes).
