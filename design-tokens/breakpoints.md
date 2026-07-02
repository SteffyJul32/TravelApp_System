# Breakpoints & Responsive Tokens

The design is **mobile-only**: every screen is an iPhone 16 frame at **393 × 852**. There are no tablet or desktop artboards, so tablet/desktop rules below are **inferred recommendations** for scaling the system up.

## Defined

| Token | Width | Source |
|-------|-------|--------|
| base (mobile) | 393px | iPhone 16 artboard (all screens) |
| content column | 343px | 393 − (2 × 25px screen padding) |

## Breakpoint scale (recommended)

| Token | Min width | Target |
|-------|-----------|--------|
| bp-mobile | 0 | Phones (design baseline, 393) |
| bp-tablet | 768px | Tablets / large phones landscape |
| bp-desktop | 1024px | Desktop / web |
| bp-wide | 1440px | Large desktop |

## Responsive rules (recommended)

- **Mobile-first:** author for 393px; layer enhancements upward. All defined tokens assume mobile.
- **Content max-width:** cap primary column at ~600px on tablet+; center it and keep the 25px→auto side padding. Don't stretch cards full-bleed on wide screens.
- **Bottom nav → side nav:** the bottom `NavBar` converts to a left sidebar at `bp-desktop`.
- **Grid:** single-column stack on mobile; image tiles (130px) flow 2–3 up on mobile and reflow to a responsive grid (`repeat(auto-fill, minmax(130px, 1fr))`) on larger screens.
- **Touch first:** preserve ≥44px targets at every breakpoint (see [accessibility.md](./accessibility.md)).
- **Screen padding scales:** 25px on mobile → 32–48px on tablet/desktop.

## Grid behaviour

- Layout is Auto Layout (flex) driven, not a fixed column grid. Vertical stack with `gap-15` between sections.
- Horizontal image rows use `gap-10`, wrapping to a fluid grid above `bp-tablet`.

## Rules

Design and test at 393px first. Introduce only the four named breakpoints; don't scatter arbitrary media queries. Preserve the token system (spacing, type, radius) across breakpoints — scale layout, not the tokens.
