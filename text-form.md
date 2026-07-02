# Text Form (Input Field)

## Description

The app's text input component, covering the common field types in the Travel app: free-text info entry, currency amounts, dropdown selection, and search. Each field is a labeled, bordered container with placeholder or entered text, and a Default vs Active (focused) appearance. This is the most variant-rich component in the library, organized on two property axes — **Type** and **Status**.

## Variants

Two properties combine into 8 published variants:

| Type | Status | Node ID |
| --- | --- | --- |
| `Info` | `Default` | `177:8245` |
| `Info` | `Active` | `177:8523` |
| `Currency` | `Default` | `177:8260` |
| `Currency` | `Active` | `177:8536` |
| `Dropdown` | `Default` | `177:8308` |
| `Dropdown` | `Active` | `177:8511` |
| `Search` | `Default` | `177:8980` |
| `Search` | `Active` | `177:9005` |

- **`Type`** — `Info`, `Currency`, `Dropdown`, `Search`
- **`Status`** — `Default`, `Active`

## States

| State | Appearance |
| --- | --- |
| Default (empty) | Border `#b0b0b0`, placeholder text `#888888`, white surface. |
| Active (focused) | Border darkens to `#5d5d5d`, entered text `#3d3d3d`. |
| Filled | Same border as default with entered value in `#3d3d3d`. |
| Error | (Extend) red border + helper text; not in base library. |
| Disabled | (Extend) muted surface + `#888888` text; non-interactive. |

> The library defines Default and Active per type. Error and Disabled are documented as required extensions.

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Type` | variant | `Info`, `Currency`, `Dropdown`, `Search` | `Info` |
| `Status` | variant | `Default`, `Active` | `Default` |
| Label | text | field label | — |
| Value / placeholder | text | any string | — |
| Leading/trailing icon | instance swap | search / currency / chevron | per type |

## Design tokens used

- **Label:** `Text/Text Form/Label Form` → `#3d3d3d`
- **Placeholder text:** `Text/Text Form/Text input Default` → `#888888`
- **Entered text:** `Text/Text Form/Text input Active` → `#3d3d3d`
- **Border default:** `Border/Text Form/Text Form Default` → `#b0b0b0`
- **Border active:** `Border/Text Form/Text Form Active` → `#5d5d5d`
- **Surface:** `Surface/Background/Background White` → `#ffffff`
- **Corner radius:** `radius-md` → 8px
- **Border width:** 1px (`stroke-1`); active may use 2px (`stroke-2`)
- **Padding:** `px-3` 12px / `py-1.5` 6px; icon gap `gap-3` 12px
- **Elevation:** `Box Shadow/shadow-xs` → `0 1 2 rgba(0,0,0,0.10)`
- **Typography:** label DM Sans `16pt Medium Subtitle` (500); input text Inter `Text-base/Regular` (16/24) and `Text-sm/Regular` (14/20)

## Accessibility guidelines

- Every field needs a programmatically associated `<label>` (not placeholder-as-label); the visible label satisfies this.
- Placeholder text (`#888888` on white) is borderline for AA — never use it as the only label, and prefer helper text for hints.
- The Active state must expose a real, visible focus indicator (the darker border) with ≥ 3:1 contrast against the default border.
- Currency/Search icons are decorative — set `aria-hidden`; the Search field should be in a `role="search"` region with a labeled control.
- Dropdown should follow the combobox/listbox ARIA pattern with keyboard support and `aria-expanded`.
- On error, convey the problem with text + `aria-invalid`/`aria-describedby`, not color alone.
- Ensure the field height gives a ≥ 44px touch target.
