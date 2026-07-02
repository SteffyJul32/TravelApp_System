# Icon Tokens

## Library style

Custom in-house glyph set (not a named third-party library). Predominantly **filled/solid single-color** glyphs that inherit color via `currentColor` from `Icons/*` semantic tokens. A few thin **outlined** directional glyphs (chevrons, arrows). Optically balanced for a 25px box.

## Sizes

| Size | Usage |
|------|-------|
| 8–10px | Inline chevrons / vectors ("See all" arrow, meta markers) |
| 25px | Standard action & category glyphs (`Icons`, `Location icon`) |
| 30px | Inline action affordances (card actions, banner CTA) |
| 40px | Bottom-nav icon frame (`Nav Icons`) |
| 45px | Large icon button |

## Stroke / fill

- Outlined glyphs: ~1.5–2px stroke at 25px, rounded joins/caps.
- Filled glyphs: solid fill, no stroke.
- Single color only — set fill/stroke to a token, never bake in hex.

## Color tokens

| Token | Value | Context |
|-------|-------|---------|
| Icons/White Icon | `#ffffff` | On brand / dark surfaces |
| Icons/Brand Icon Default | `#267421` | On light surfaces (resting) |
| Icons/Brand Icon Active | `#1f511d` | Active/pressed brand icon |
| Icons/MenuNav Icon Default | `#4f4f4f` | Inactive bottom-nav |
| Icons/MenuNav Icon Active | `#235c1f` | Active bottom-nav |

## Detected categories

- **Navigation:** Home, Trip, Budget, Transport (`Nav Icons`)
- **Actions:** Add, Map, List (`Icons`)
- **Place / location:** Airport, Shop, Food, Landmark (`Location icon`)
- **Directional / utility:** chevron/arrow ("See all", back), plus small vector markers

## Filled vs outlined

Filled is the default and dominant treatment (nav, categories, actions). Outlined is reserved for directional/utility affordances. Don't mix treatments within one row or control group.

## Rules

Use 25px as the default glyph size; 40px only inside nav frames. Color exclusively through `Icons/*` tokens. Icons paired with a visible text label are decorative (`aria-hidden`); icon-only controls need an accessible name — see [accessibility.md](./accessibility.md).
