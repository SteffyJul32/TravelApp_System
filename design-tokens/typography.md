# Typography Tokens

Two families. **DM Sans** = all display/UI text (headings, titles, labels, buttons, nav). **Inter** (`family/sans`) = form inputs and long-form body. DM Sans styles render at `lineHeight: 100%` (≈ normal) with `letterSpacing: 0` and `opsz 14`.

## Primitives (variables)

- Family: `Font/Font Family/Font Family` = **DM Sans**; `family/sans` = **Inter**
- Weights: `Regular` 400, `Medium` 500, `Semi Bold` 600, `Bold` 700
- Sizes: `size/xs` 12 · `size/sm` 14 · `size/base` 16 · `size/lg` 18 · `size/2xl` 24 · (also 10, 11 literal)
- Line height: DM Sans `100%`; Inter `leading/5` 20, `leading/6` 24
- Tracking: `tracking/normal` 0

## Type scale (DM Sans / display + UI)

| Token | Family | Size | Weight | Line Height | Usage |
|-------|--------|------|--------|-------------|-------|
| Bold Title 24pt | DM Sans | 24 | 700 | 100% | Display — screen greeting / page title |
| Bold Title 18pt | DM Sans | 18 | 700 | 100% | H1 — section hero, banner headline |
| 16pt Bold Title | DM Sans | 16 | 700 | 100% | H2 — section header, card title, nav label |
| 16pt SemiBold Title | DM Sans | 16 | 600 | 100% | H2 alt — inactive nav label |
| 16pt Medium Subtitle | DM Sans | 16 | 500 | 100% | Form label, emphasized body |
| 14pt Bold Title | DM Sans | 14 | 700 | 100% | H3 / text button, active tab |
| 14pt Medium Subtitle | DM Sans | 14 | 500 | 100% | Default tab, secondary label |
| Semibold Subtitle 12pt | DM Sans | 12 | 600 | 100% | Emphasized caption |
| Medium Subtitle 12pt | DM Sans | 12 | 500 | 100% | Meta text (dates, counts) |
| 11pt Semibold Caption | DM Sans | 11 | 600 | 100% | Caption emphasis |
| 11pt Medium Caption | DM Sans | 11 | 500 | 100% | Caption, avatar meta |
| Semibold Time 10pt | DM Sans | 10 | 600 | 100% | Timestamps, micro-labels |

## Body / input (Inter)

| Token | Family | Size | Weight | Line Height | Usage |
|-------|--------|------|--------|-------------|-------|
| Text-base/Regular | Inter | 16 | 400 | 24 | Input value, body paragraph |
| Text-sm/Regular | Inter | 14 | 400 | 20 | Helper text, dense body |
| Text-sm/Medium | Inter | 14 | 500 | 20 | Emphasized helper / inline label |

## Roles

- **Display:** Bold Title 24pt
- **Headings:** 18pt Bold → 16pt Bold/SemiBold → 14pt Bold (H1→H3)
- **Body:** Inter Text-base/Regular (16/24), Text-sm/Regular (14/20)
- **Captions:** 12pt & 11pt DM Sans, 10pt for time
- **Buttons:** 16pt SemiBold (primary), 14pt Bold (text button)

## Rules

Use DM Sans for anything structural/UI, Inter only for input + running text. Never introduce a size outside {10,11,12,14,16,18,24}. Line height 100% is intentional for tight DM Sans headings; give Inter body its 20/24 leading for readability. Don't add new weights — map to 400/500/600/700.
