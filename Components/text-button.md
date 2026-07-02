# Text Button

## Description

A low-emphasis, label-only button with no container fill or border. Used for tertiary actions and inline navigation such as "See all", "Skip", "Edit", or "Cancel", where a full filled button would be visually too heavy. The brand green label signals interactivity without competing with primary buttons.

## Variants

The component is delivered as a single base symbol (`161:4878`). It has no named variant axis; visual differences are driven by the label text and, optionally, a leading brand icon.

## States

| State | Appearance |
| --- | --- |
| Default / Enabled | Green 700 (`#235c1f`) label, transparent background. |
| Hover (web) | Underline or shift toward Green 800 (`#1f511d`). |
| Pressed / Active | Green 800 (`#1f511d`). |
| Focus | Focus ring around the label bounds. |
| Disabled | Black 300 (`#888888`) label, non-interactive. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| Label | text | any string | "Button" |
| Leading icon | instance swap (optional) | brand icon | — |

## Design tokens used

- **Text:** `Text/Button Text/Brand text` → Green 700 `#235c1f`
- **Icon (optional):** `Icons/Brand Icon Default` → `#267421`
- **Typography:** DM Sans, `14pt DMSans/Bold Title` (700)
- **Background:** none (transparent)
- **Padding:** minimal; keep hit target ≥ 44px tall even though the visual text is smaller

## Accessibility guidelines

- Use a real `<button>` element so it is keyboard-operable, not a styled `<span>`.
- Green 700 text on white meets AA contrast; verify on any tinted background it is used over.
- Because the visual footprint is small, expand the touch/click target to at least 44×44px.
- If hover adds an underline, do not rely on color alone to indicate the button is interactive — the label wording and focus state should also convey it.
- Provide a clear, verb-first accessible name.
