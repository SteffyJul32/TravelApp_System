# Border Radius Tokens

One radius variable is defined (`radius-md` = 8), but layouts predominantly use a raw **10px** on cards and images. Treat this as a token gap: standardize on the scale below and tokenize 10px.

| Token | Value | Common Usage |
|-------|-------|--------------|
| radius-sm *(proposed)* | 4 | Chips, small tags |
| radius-md | 8 | Inputs, buttons (`Text Form`, `Button`) |
| radius-lg *(from raw 10px)* | 10 | Cards, image tiles, banners, thumbnails, bottom sheet corners |
| radius-full | 999 / 50% | Avatars & circular pills (raw `35px` on ≤35px elements) |

## Observed usage

- Cards / banners / trip thumbnails: `rounded-[10px]` (top corners only when image sits above content: `rounded-t-[10px]`).
- Image tiles: `rounded-[10px]`.
- Inputs & buttons: `radius-md` (8).
- Avatars ("Prof"), status pills: `rounded-[35px]` on 20–35px elements = fully round.

## Rules

- Use `radius-md` (8) for interactive controls; `radius-lg` (10) for containers/media.
- Circular elements use `radius-full`, not a literal 35px.
- Never introduce intermediate values (9, 12, 16). Reconcile the 8 vs 10 split by picking one per element class (controls = 8, containers = 10) and keep it consistent.
