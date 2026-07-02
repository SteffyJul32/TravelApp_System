# Fill (List Row)

## Description

A horizontal list row used to present a location, itinerary item, or budget line in a scrollable list. It typically pairs a leading [Location Icon](./location-icon.md), a primary label and secondary text, and a trailing value or chevron. The variants adapt the same row to a plain content item, a budget line with an amount, and an alternate layout.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Default` | `163:5065` | Standard content row — leading icon, title, subtitle. |
| `Budget` | `175:7493` | Row with a trailing amount/cost value. |
| `Variant3` | `180:10106` | Alternate row layout (e.g. different trailing element or density). |

Property name: **`Property 1`** with values `Default`, `Budget`, `Variant3`.

## States

| State | Appearance |
| --- | --- |
| Default | White surface, title + subtitle, optional divider. |
| Hover (web) | Light brand tint (`#e2f8e0`) background. |
| Pressed | Brief highlight before navigation. |
| Focus | Focus ring around the row. |
| Selected | Brand-tinted background / brand icon. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Default`, `Budget`, `Variant3` | `Default` |
| Leading icon | instance swap | Location Icon | — |
| Title | text | primary label | — |
| Subtitle | text | secondary label | — |
| Amount | text | currency value | — (Budget) |

## Design tokens used

- **Surface:** `Surface/Background/Background White` → `#ffffff`
- **Title:** `Text/Text/Title` → `#000000`, DM Sans SemiBold/Bold 16pt
- **Subtitle:** `Text/Text/Subtitle` → `#3d3d3d`, DM Sans/Inter 12–14pt
- **Icon:** `Icons/Brand Icon Default` → `#267421`
- **Hover/selected tint:** `Surface/Background/Background Light` → `#e2f8e0`
- **Padding:** `px-3` 12px horizontal, `py-2` 8px vertical; `gap-3` 12px between icon and text
- **Corner radius (card form):** `radius-md` 8px

## Accessibility guidelines

- If the whole row navigates or selects, make it one interactive element with a combined accessible name (title + value), not several nested tab stops.
- Provide a text alternative for the leading category icon or mark it decorative when the title already conveys the item.
- For the Budget variant, ensure the amount is part of the row's accessible name and doesn't rely on color (e.g. red/green) to convey over/under budget.
- Maintain AA contrast for title and subtitle on white; keep row height ≥ 44px for touch.
- Use list semantics (`<ul>/<li>` or `role="list"`) so assistive tech announces position and count.
