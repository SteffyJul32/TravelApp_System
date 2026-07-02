# Image

## Description

A reusable media placeholder that reserves a fixed area for photographic content — trip covers, destination photos, and banner backgrounds. It standardizes aspect handling and corner rounding so imagery is consistent across [Trip Thumbnail](./trip-thumbnail.md), [Banner Template](./banner-template.md), and detail screens. Designers swap the fill with a real photo; in code it maps to an `<img>` / background with object-fit cropping.

## Variants

Delivered as a single base symbol (`161:4869`, 130 × 130px in the library). No named variant axis — sizing and ratio are controlled by the container it is placed in via layout constraints.

## States

| State | Appearance |
| --- | --- |
| Loaded | The supplied photo, cropped to fill and clipped to the corner radius. |
| Loading | Neutral placeholder fill (Black 50 `#e7e7e7`) or shimmer. |
| Empty / error | Fallback placeholder graphic on a neutral surface. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| Source | image fill | any photo | placeholder |
| Fit | scale mode | fill / fit | fill (crop) |
| Corner radius | number | inherits container | `radius-md` 8px |

## Design tokens used

- **Placeholder surface:** Black 50 `#e7e7e7` / Black 100 `#d1d1d1`
- **Corner radius:** `radius-md` 8px (or fully rounded where used as an avatar)
- **Default frame:** 130 × 130px (resizes to container)

## Accessibility guidelines

- Always supply descriptive `alt` text for content images; use empty `alt=""` (and `aria-hidden`) only when the image is purely decorative and its meaning is already in adjacent text.
- Don't put text inside the raster image — keep captions and labels as real text so they scale and are readable by assistive tech.
- Provide a stable placeholder to avoid layout shift while loading, and a graceful fallback on error.
- Ensure any text overlaid on the image (via Banner/Thumbnail) keeps ≥ 4.5:1 contrast, adding a scrim if needed.
- Do not convey essential information through imagery alone.
