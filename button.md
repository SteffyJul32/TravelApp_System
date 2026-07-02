# Button

## Description

The primary action control of the Travel app. Button is a full-width, brand-colored container used for the main call-to-action on a screen (e.g. "Continue", "Save trip", "Add expense"). It renders on a solid green surface with white label text and optional leading icon, communicating the single most important action in the current context.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Default` | `161:5044` | Label-only button. Used when the action is self-explanatory from its text. |
| `With Icon` | `161:5042` | Leading white icon + label. Used to reinforce the action's meaning (e.g. a plus glyph for "Add"). |

Property name: **`Property 1`** with values `Default` and `With Icon`.

## States

| State | Appearance |
| --- | --- |
| Default / Enabled | Green 700 (`#235c1f`) surface, white text/icon. |
| Hover (web) | Darken surface one step toward Green 800 (`#1f511d`). |
| Pressed / Active | Green 800 (`#1f511d`), optional inset feedback. |
| Focus | Visible focus ring (2px, Green 600 `#267421`) offset from the surface. |
| Disabled | Reduce to Black 100 (`#d1d1d1`) surface with Black 300 (`#888888`) text; non-interactive. |

> Note: Only the Default and Enabled states are drawn in the Figma library. Hover, pressed, focus, and disabled are documented here as required implementation behavior.

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Default`, `With Icon` | `Default` |
| Label | text | any string | "Button" |
| Leading icon | instance swap | any 24px icon | — (With Icon only) |

## Design tokens used

- **Surface:** `Surface/Button/Button Default` → Green 700 `#235c1f`
- **Text:** `Text/Button Text/White text` → `#ffffff`
- **Icon:** `Icons/White Icon` → `#ffffff`
- **Corner radius:** `radius-md` → 8px
- **Height:** 48px
- **Padding:** horizontal `px-3` 12px, vertical `py-2` 8px; icon-to-label `gap-3` 12px
- **Typography:** DM Sans, `16pt DMSans/SemiBold Title` (600) or `14pt Medium Subtitle` for compact contexts

## Accessibility guidelines

- Use a native `<button>` (or role="button") so it is keyboard-focusable and Enter/Space activates it.
- Green 700 on white text meets WCAG AA for contrast (ratio ≈ 7.8:1); verify any hover/pressed shade stays ≥ 4.5:1.
- Provide a descriptive, action-oriented label ("Save trip", not "OK"). For the With Icon variant, the icon is decorative — the text label carries the accessible name.
- Ensure a minimum 44×44px touch target; the 48px height satisfies this.
- Maintain a visible focus indicator distinct from hover.
- Never rely on color alone to signal the disabled state — pair it with `aria-disabled` / the `disabled` attribute.
