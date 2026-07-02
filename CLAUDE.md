# Design System Rules

This project has a documented design system. **Read tokens before writing UI code** and follow these rules to keep output consistent and low-token.

## Core rules

- Always use tokens from `/design-tokens`.
- Never introduce new colors.
- Never introduce new typography scales.
- Never introduce arbitrary spacing values.
- Reuse existing patterns before creating new ones.
- Follow accessibility guidelines.
- Prefer semantic tokens over raw values.
- Maintain visual consistency across all screens.

## Source of truth

Figma Variables are canonical. Use variable names exactly as defined (e.g. `Surface/Button/Button Default`, `Text/Text/Title`, `radius-md`). When a value is needed but no token exists, add a **new semantic token** to the relevant file — never hardcode a hex, px, or ad-hoc style.

## Where things live

| Need | File |
|------|------|
| Colors (brand/neutral/semantic/status) | `design-tokens/colors.md` |
| Text styles & scale | `design-tokens/typography.md` |
| Spacing & Auto Layout rhythm | `design-tokens/spacing.md` |
| Border radius | `design-tokens/radius.md` |
| Shadows / elevation | `design-tokens/shadows.md` |
| Icon sizing & styles | `design-tokens/icons.md` |
| Motion / transitions | `design-tokens/motion.md` |
| Breakpoints / responsive | `design-tokens/breakpoints.md` |
| A11y standards & contrast | `design-tokens/accessibility.md` |
| Role → value mapping | `design-tokens/semantic-tokens.md` |
| Screen composition | `patterns/layout-patterns.md` |
| Navigation | `patterns/navigation-patterns.md` |
| Onboarding | `patterns/onboarding-patterns.md` |
| Empty / error states | `patterns/empty-states.md` |
| Individual components | `components/*.md` |

## Foundations quick reference

- **Platform:** mobile-first, iPhone 16 (393×852). 25px screen padding. Section `gap-15`.
- **Type:** DM Sans (UI/headings) + Inter (body/inputs). Sizes 10/11/12/14/16/18/24 only.
- **Color:** Green ramp (brand, primary = Green 700 `#235c1f`) + Black ramp (neutrals). Green 50 `#e2f8e0` = tint.
- **Radius:** 8 (controls) / 10 (containers) / full (avatars).
- **Elevation:** two levels — `shadow-xs`, `shadow`.

## Known gaps (add tokens, don't improvise)

Status colors (success/error/warning/info), focus-ring token, hover/pressed button states, app-canvas color `#f0f2f0`, and the 8-vs-10 radius split are not fully tokenized. Introduce proper semantic tokens for these rather than raw values. See `accessibility.md` for contrast items (`#888888` text, `#b0b0b0` borders).
