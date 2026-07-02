# Snackbar

## Description

A transient, non-modal message shown near the bottom of the screen to confirm an action or surface a brief status (e.g. "Trip saved", "Expense added"). It appears on top of content, auto-dismisses after a short timeout, and may include a single inline action. Two layout variants cover a plain message and a message-with-action/icon.

## Variants

| Variant | Node ID | Description |
| --- | --- | --- |
| `Default` | `175:6838` | Message text only. |
| `Variant2` | `193:1125` | Message with an accompanying icon and/or trailing action. |

Property name: **`Property 1`** with values `Default` and `Variant2`.

## States

| State | Behavior |
| --- | --- |
| Entering | Slides/fades up from the bottom. |
| Visible | Rests above content with a drop shadow for elevation. |
| Action hover/focus | Trailing action shows hover + focus styling (Variant2). |
| Exiting | Fades/slides out after timeout or on action. |

## Properties

| Property | Type | Values | Default |
| --- | --- | --- | --- |
| `Property 1` | variant | `Default`, `Variant2` | `Default` |
| Message | text | short string | — |
| Leading icon | instance swap (optional) | icon | — (Variant2) |
| Action | text button (optional) | e.g. "Undo" | — (Variant2) |

## Design tokens used

- **Surface:** dark neutral (Black 800 `#3d3d3d` / Black 950 `#000000`) for contrast over content
- **Text:** DM Sans `14pt Medium Subtitle` (500), white `#ffffff`
- **Elevation:** `shadow` → `0 4 6 rgba(0,0,0,0.09)`
- **Corner radius:** `radius-md` 8px
- **Padding:** `px-3` 12px / `py-2` 8px; `gap-3` 12px between message and action
- **Width:** ~345px content, near-full-width with side margins

## Accessibility guidelines

- Announce the message to assistive tech with a live region: `role="status"` (`aria-live="polite"`) for confirmations, `role="alert"` for errors.
- Do not put critical or irreversible information only in a Snackbar — it auto-dismisses and may be missed.
- If it contains an action (e.g. "Undo"), keep the Snackbar visible long enough to reach, and make the action keyboard-focusable; give it an accessible name.
- Ensure the auto-dismiss timeout is generous (WCAG 2.2.1 timing) or pausable; don't dismiss on the very first timer if an action is present.
- White text on the dark surface easily meets AA; verify any icon meets 3:1 non-text contrast.
- Position so it does not obscure the primary [Button](./button.md) or bottom [NavBar](./navbar.md) permanently.
