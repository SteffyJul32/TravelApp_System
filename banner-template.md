# Banner Template

## Description

A promotional / informational banner block used to feature content on the home and trip screens — for example a highlighted destination, a tip, or a call-to-action card. Delivered as a fixed-ratio template (≈343 × 200px) with an image or color background and space for a headline, supporting text, and an optional action. It is a composition scaffold: designers swap in copy, imagery, and a [Text Button](./text-button.md) or [Button](./button.md).

## Variants

Delivered as a single base symbol (`161:4841`) with no named variant axis. Content is customized through layer overrides (background, headline, body, action) rather than component properties.

## States

| State | Appearance |
| --- | --- |
| Default | Static banner with background media and overlaid text. |
| Interactive (optional) | If the whole banner is tappable: hover elevation and pressed feedback. |
| Focus | Focus ring when the banner (or its action) is focusable. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| Background | fill / image swap | color or [Image](./image.md) | — |
| Headline | text | short string | — |
| Body | text | supporting copy | — |
| Action | instance swap (optional) | Button / Text Button | — |

## Design tokens used

- **Size / ratio:** 343 × 200px template frame
- **Corner radius:** `radius-md` 8px
- **Title:** DM Sans `16pt Bold Title` (700), `Text/Text/Title` `#000000` (or white over dark imagery)
- **Body:** `Text/Text/Subtitle` `#3d3d3d`
- **Brand accents:** Green 700 `#235c1f`, Green 50 `#e2f8e0`
- **Elevation:** `shadow` `0 4 6 rgba(0,0,0,0.09)` when raised

## Accessibility guidelines

- If text is placed over an image, guarantee ≥ 4.5:1 contrast for the headline/body — add a scrim/overlay when the background is busy.
- Provide meaningful `alt` text for a content-bearing background image, or mark it decorative if the headline conveys everything.
- If the entire banner is a link/button, give it one clear accessible name and a visible focus ring; avoid nesting a separate focusable action inside a focusable banner.
- Don't encode essential meaning in the background image alone; keep it in the text layers.
- Keep any embedded action a ≥ 44px target.
