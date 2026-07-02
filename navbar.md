# NavBar (Bottom Navigation Item)

## Description

A single item in the app's bottom navigation bar, pairing an icon with a text label to represent a top-level destination (Home, Budget, Trip, Transport). It has a resting and a selected appearance so the user always knows which section they are in. Compose multiple NavBar items with the [Nav Icons](./nav-icons.md) set to build the full bottom bar.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Default` | `149:395` | Inactive destination — neutral icon and label. |
| `Active` | `149:397` | Current destination — brand icon and black label. |

Property name: **`Property 1`** with values `Default` and `Active`.

## States

| State | Appearance |
| --- | --- |
| Default | Icon `Icons/MenuNav Icon Default` (Black 600 `#4f4f4f`), label `#4f4f4f`, SemiBold. |
| Active | Icon `Icons/MenuNav Icon Active` (Green 700 `#235c1f`), label black (`#000000`), Bold. |
| Pressed | Brief highlight on tap before selection resolves. |
| Focus | Focus ring around the item. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Default`, `Active` | `Default` |
| Icon | instance swap | Home / Budget / Trip / Transport | Home |
| Label | text | destination name | — |

## Design tokens used

- **Icon default:** `Icons/MenuNav Icon Default` → `#4f4f4f`
- **Icon active:** `Icons/MenuNav Icon Active` → `#235c1f`
- **Label default:** `Text/MenuNav Text/MenuNav Default` → `#4f4f4f`
- **Label active:** `Text/MenuNav Text/MenuNav Active` → `#000000`
- **Typography:** DM Sans — default `16pt SemiBold Title` (600), active `16pt Bold Title` (700); caption-scale labels use 11pt DM Sans in the bar context
- Icon + label stacked vertically, centered

## Accessibility guidelines

- Use the navigation landmark: wrap items in `<nav aria-label="Primary">` and mark the current item with `aria-current="page"`.
- Selection is conveyed by color **and** weight (SemiBold → Bold) plus `aria-current`, so it does not depend on color alone.
- Each item must be a full-height tap target of at least 44×44px.
- Provide a text label for every icon (don't ship icon-only bottom nav); the label is the accessible name.
- Verify Black 600 label/icon on white meets AA (≈ 7:1 — passes).
