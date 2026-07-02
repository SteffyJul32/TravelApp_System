# Trip Thumbnail

## Description

A card that previews a trip in a list or grid. It combines a cover image with a title, subtitle/date, and supporting metadata. The Budget variant reframes the same card to foreground a spending summary instead of a photo-led preview, so the component serves both the "my trips" browse view and the budget overview.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Trip` | `161:4850` | Photo-led trip preview card with title and subtitle. |
| `Budget` | `175:7000` | Budget-focused card emphasizing amounts/summary. |

Property name: **`Property 1`** with values `Trip` and `Budget`.

## States

| State | Appearance |
| --- | --- |
| Default | Resting card on white surface with subtle card border. |
| Hover (web) | Slight elevation increase. |
| Pressed | Brief highlight before navigation. |
| Focus | Focus ring around the card. |
| Loading | Image area shows a placeholder ([Image](./image.md) component). |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Trip`, `Budget` | `Trip` |
| Title | text | trip name | — |
| Subtitle | text | dates / summary | — |
| Cover image | instance swap | Image | — |

## Design tokens used

- **Title:** `Text/Text/Title` → `#000000`, DM Sans `16pt Bold Title` (700)
- **Subtitle:** `Text/Text/Subtitle` → `#3d3d3d`, DM Sans `12pt Medium Subtitle` (500)
- **Caption/meta:** `11pt DMSans Semibold/Medium Caption`; time uses `10pt Semibold Time`
- **Surface:** `Surface/Button/White Default` → `#ffffff`
- **Border:** `Border/Card/Card Default` → `#f6f6f6`
- **Elevation:** `shadow` → `0 4 6 rgba(0,0,0,0.09)`
- **Brand accent (budget):** `Icons/Brand Icon Default` `#267421`, `Surface/Background/Background Light` `#e2f8e0`
- **Corner radius:** `radius-md` 8px

## Accessibility guidelines

- Make the whole card a single activatable target with one accessible name (title + dates) rather than multiple competing tab stops.
- Provide meaningful `alt` text on the cover image, or mark it decorative if the title already conveys the trip.
- Ensure the title/subtitle color pairing meets AA (Black on white and Black 800 on white both pass).
- Preserve a visible focus ring on the card container.
- For the Budget variant, don't convey positive/negative spend by color alone — include a label or sign.
