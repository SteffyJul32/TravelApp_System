# Location (Map Pin)

## Description

A map marker that pins a place on the trip map. It hosts a [Location Icon](./location-icon.md) inside a rounded, brand-tinted pin and supports a resting, selected, and budget-annotated form. The Active variant is enlarged/darkened to show the currently focused stop; the Budget variant surfaces a cost figure directly on the map.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Default` | `171:5275` | Resting pin — light brand surface, brand icon. |
| `Active` | `171:5277` | Selected/focused pin — darker brand fill, elevated. |
| `Budget` | `175:7515` | Pin that also displays a price/amount for the stop. |

Property name: **`Property 1`** with values `Default`, `Active`, `Budget`.

## States

| State | Appearance |
| --- | --- |
| Default | `Surface/Background/Background Light` (`#e2f8e0`) with `Icons/Brand Icon Default` (`#267421`). |
| Active | Deeper brand fill; icon `Icons/Brand Icon Active` (`#1f511d`); raised with shadow. |
| Budget | Default pin form plus an amount label. |
| Focus | Focus ring around the pin bounds (keyboard map navigation). |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Default`, `Active`, `Budget` | `Default` |
| Category icon | instance swap | Airport / Shop / Food / Landmark | — |
| Amount | text | currency string | — (Budget only) |

## Design tokens used

- **Surface (default):** `Surface/Background/Background Light` → `#e2f8e0` (Green 50)
- **Icon default:** `Icons/Brand Icon Default` → `#267421`
- **Icon active:** `Icons/Brand Icon Active` → `#1f511d`
- **Icon on filled pin:** `Icons/White Icon` → `#ffffff`
- **Elevation:** `shadow` → `0 4 6 rgba(0,0,0,0.09)`
- **Size:** 40–45px pin body

## Accessibility guidelines

- Map pins must be keyboard reachable and operable — expose each as a button with an accessible name that includes the place name and category (e.g. "Louvre, landmark").
- The selected/Active state must be conveyed programmatically (`aria-pressed` / `aria-current`), not by color and size alone.
- For the Budget variant, ensure the amount text meets AA contrast against the pin surface and is announced together with the place name.
- Provide a non-map alternative (the [Fill](./fill.md) list view) so users who cannot interact with the map can reach the same locations.
- Maintain ≥ 44px touch target for pins on touch devices.
