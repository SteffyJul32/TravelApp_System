# Spacing Tokens

Two coexisting rhythms. Component-internal padding uses a **4px-based** variable scale (source of truth). Screen/section layout uses a **5px-based** rhythm (5/10/15/25) applied as raw Auto Layout gaps. Consolidate toward the 4px scale where possible; the 5px values are candidates to tokenize.

## Scale (Figma variables — component padding)

| Token | Value |
|-------|-------|
| py-1 | 4 |
| py-1.5 | 6 |
| px-2 / py-2 / pl-2 | 8 |
| px-3 / pl-3 / pr-3 / gap-3 | 12 |

## Layout rhythm (Auto Layout gaps, observed)

| Token (proposed) | Value | Where |
|------|-------|-------|
| gap-2xs | 2 | Title→subtitle within a text block |
| gap-xs | 5 | Tight groups (icon clusters, list sub-rows) |
| gap-sm | 10 | Related items, image row, card content padding |
| gap-md | 15 | Between page sections |
| pad-screen | 25 | Left/right screen padding |

## Derived layout constants

- **Screen frame:** 393 × 852 (iPhone 16)
- **Content column:** 343px wide, offset `left: 25`, `top: 65` → **25px horizontal screen padding**
- **Card content padding:** `px-15 py-10`
- **Bottom nav bar:** full-width 393, `px-10 pb-10`, item `gap-10`
- **Thumbnail tile:** 130 × 130, inner `p-10`

## Rules

- Prefer the 4px token scale (4/6/8/12) for padding inside components.
- Use the layout rhythm (5/10/15/25) for spacing *between* components and sections; 15 separates sections, 10 groups related items, 5 is intra-group.
- Screen horizontal padding is always **25px** — do not deviate per screen.
- Never invent one-off values (e.g. 7, 13, 22). Snap to the nearest token.
- Vertical section stacks use `gap-15`; card internals use `px-15 py-10`.
