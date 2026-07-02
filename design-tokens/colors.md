# Color Tokens

Source of truth: Figma Variables. Primitive ramps (`Green`, `Black`) are raw values; **always reference the semantic token, not the hex**. Two primitives are used but not yet in a ramp and should be tokenized: app canvas `#f0f2f0` and card border `#f6f6f6`.

## Brand colors (Green ramp)

| Token | Value | Usage |
|-------|-------|-------|
| Green 950 | `#0a290a` | Deepest brand; reserved / high-emphasis text on light |
| Green 800 | `#1f511d` | Avatars, pressed brand states, active icons |
| Green 700 | `#235c1f` | **Primary** — button fill, brand text, active nav icon |
| Green 600 | `#267421` | Active surfaces, selected borders, default brand icon |
| Green 500 | `#2d9326` | Accent / illustration |
| Green 400 | `#3db235` | Accent / illustration |
| Green 300 | `#63cd5b` | Accent / illustration |
| Green 200 | `#98e392` | Subtle accent |
| Green 100 | `#c6f0c2` | Tint background |
| Green 50 | `#e2f8e0` | Lightest brand tint — selected/hover backgrounds |

## Neutral colors (Black ramp)

| Token | Value | Usage |
|-------|-------|-------|
| Black 950 | `#000000` | Titles, active nav label (`Text/Text/Title`, `Labels/Primary`) |
| Black 800 | `#3d3d3d` | Subtitles, input text, form labels |
| Black 700 | `#454545` | Secondary body text |
| Black 600 | `#4f4f4f` | Default nav label & icon |
| Black 500 | `#5d5d5d` | Active input border |
| Black 400 | `#6d6d6d` | Muted meta text |
| Black 300 | `#888888` | Placeholder / disabled text, default button text |
| Black 200 | `#b0b0b0` | Default input & tab border |
| Black 100 | `#d1d1d1` | Disabled surface (`Background Default`) |
| Black 50 | `#e7e7e7` | Image/skeleton placeholder |
| White | `#ffffff` | Surfaces, text on brand (`Colour/Black/White`) |

## Surface / background

| Token | Value | Usage |
|-------|-------|-------|
| Surface/Background/Background White | `#ffffff` | Cards, sheets, inputs |
| Surface/Background/Background Light | `#e2f8e0` | Selected/hover rows, budget pins, tints |
| Surface/Background/Background Active | `#267421` | Selected date cell, active fills |
| Surface/Background/Background Default | `#d1d1d1` | Disabled control surface |
| Surface/Button/Button Default | `#235c1f` | Primary button fill |
| Surface/Button/White Default | `#ffffff` | Secondary/white button fill |
| App background *(untokenized)* | `#f0f2f0` | Screen canvas behind content — **tokenize as `Surface/App`** |

## Status colors

The library ships **no dedicated success / warning / error / info tokens**. Green is overloaded as both brand and implied success. Recommended additions (WCAG-AA on white):

| Proposed token | Value | Usage |
|-------|-------|-------|
| Status/Success | `#267421` (reuse Green 600) | Confirmations |
| Status/Error | `#c62828` | Field errors, destructive |
| Status/Warning | `#b26a00` | Cautions |
| Status/Info | `#1f6feb` | Neutral info |

> Add these before shipping error/validation states; see [accessibility.md](./accessibility.md).

## Semantic text / icon / border

Defined as variables — see [semantic-tokens.md](./semantic-tokens.md) for the full role map (`Text/*`, `Icons/*`, `Border/*`).
