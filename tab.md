# Tab

## Description

A single tab item used within a horizontal tab bar to switch between sibling views (for example "Overview" / "Itinerary" / "Budget"). Each Tab shows a text label and a bottom indicator border; the selected tab is emphasized with brand color and a heavier weight.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Active` | `161:4925` | Currently selected tab — brand text and brand underline. |
| `Default` | `171:5875` | Unselected tab — muted text and neutral underline. |

Property name: **`Property 1`** with values `Active` and `Default`.

## States

| State | Appearance |
| --- | --- |
| Default (unselected) | Black 300 (`#888888`) label, Black 200 (`#b0b0b0`) bottom border, Medium weight. |
| Active (selected) | Green 700 (`#235c1f`) label, Green 600 (`#267421`) bottom border, Bold weight. |
| Hover (unselected) | Label darkens toward Black 800; indicator hints brand color. |
| Focus | Focus ring around the tab label. |
| Disabled | Reduced-opacity label, no indicator, non-interactive. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Active`, `Default` | `Default` |
| Label | text | any string | tab name |

## Design tokens used

- **Active text:** `Text/Button Text/Brand text` → `#235c1f`
- **Default text:** `Text/Button Text/Default text` → `#888888`
- **Active indicator:** `Border/Tab/Tab Active` → `#267421`
- **Default indicator:** `Border/Tab/Tab Default` → `#b0b0b0`
- **Typography:** DM Sans — Active `14pt DMSans/Bold Title` (700), Default `14pt DMSans/Medium Subtitle` (500)
- **Border width:** 1–2px bottom indicator

## Accessibility guidelines

- Implement with the WAI-ARIA Tabs pattern: `role="tablist"` on the container, `role="tab"` on each Tab, and `aria-selected="true"` on the active tab.
- Support arrow-key navigation between tabs and Tab key to move focus into the panel; associate each tab to its panel via `aria-controls`.
- Do not signal selection with color only — the weight change (Bold vs Medium) and the `aria-selected` state provide non-color cues.
- Ensure the label text meets AA contrast in both states (Black 300 on white is borderline for small text; prefer Black 600 `#4f4f4f` if the label is below 14px).
- Keep each tap target ≥ 44px tall.
