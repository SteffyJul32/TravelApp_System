# Semantic Tokens

Role-based mapping from raw values to intent. **Reference these, not hex.** Names match Figma variables where they exist; *(proposed)* marks recommended additions. Values cross-reference [colors.md](./colors.md), [typography.md](./typography.md), [radius.md](./radius.md), [shadows.md](./shadows.md).

## Semantic variable index (from Figma)

| Role | Variable | Value |
|------|----------|-------|
| Title text | `Text/Text/Title`, `Labels/Primary` | Black 950 `#000000` |
| Subtitle text | `Text/Text/Subtitle` | Black 800 `#3d3d3d` |
| Brand text | `Text/Button Text/Brand text` | Green 700 `#235c1f` |
| On-brand text | `Text/Button Text/White text` | White `#ffffff` |
| Muted/disabled text | `Text/Button Text/Default text` | Black 300 `#888888` |
| Form label | `Text/Text Form/Label Form` | Black 800 `#3d3d3d` |
| Input placeholder | `Text/Text Form/Text input Default` | Black 300 `#888888` |
| Input value | `Text/Text Form/Text input Active` | Black 800 `#3d3d3d` |
| Nav label default / active | `Text/MenuNav Text/*` | `#4f4f4f` / `#000000` |
| Brand icon default / active | `Icons/Brand Icon *` | `#267421` / `#1f511d` |
| Nav icon default / active | `Icons/MenuNav Icon *` | `#4f4f4f` / `#235c1f` |
| Icon on brand | `Icons/White Icon` | `#ffffff` |
| Input border default / active | `Border/Text Form/*` | `#b0b0b0` / `#5d5d5d` |
| Tab border default / active | `Border/Tab/*` | `#b0b0b0` / `#267421` |
| Card border | `Border/Card/Card Default` | `#f6f6f6` |
| Primary surface | `Surface/Button/Button Default` | `#235c1f` |
| Tint / selected surface | `Surface/Background/Background Light` | `#e2f8e0` |
| Active surface | `Surface/Background/Background Active` | `#267421` |
| Disabled surface | `Surface/Background/Background Default` | `#d1d1d1` |
| White surface | `Surface/Background/Background White` | `#ffffff` |

## Component semantic maps

### Primary Button
- Background: `Surface/Button/Button Default` (Green 700)
- Text/Icon: `Text/Button Text/White text` / `Icons/White Icon`
- Radius: `radius-md` (8) · Height: 48 · Padding: `px-3 py-2` · Gap: `gap-3`
- Typography: 16pt SemiBold Title
- Hover/Pressed *(proposed)*: Green 800 `#1f511d` · Disabled: `Background Default` + `Default text`

### Text / Secondary Button
- Background: transparent (or `Surface/Button/White Default`)
- Text: `Text/Button Text/Brand text` · Typography: 14pt Bold Title

### Navigation (bottom nav)
- Default: icon `Icons/MenuNav Icon Default`, label `Text/MenuNav Text/MenuNav Default`, weight SemiBold
- Active: icon `Icons/MenuNav Icon Active`, label `Text/MenuNav Text/MenuNav Active`, weight Bold, `aria-current="page"`
- Bar surface: white, `px-10 pb-10`, item `gap-10`

### Tabs
- Default: text `Default text`, border `Border/Tab/Tab Default`, 14pt Medium
- Active: text `Brand text`, border `Border/Tab/Tab Active`, 14pt Bold, `aria-selected`

### Cards (trip thumbnail / banner / list row)
- Background: `Surface/Background/Background White`
- Border: `Border/Card/Card Default` (`#f6f6f6`)
- Elevation: `shadow` · Radius: `radius-lg` (10)
- Title: `Text/Text/Title` 16pt Bold · Meta: `Text/Text/Subtitle` 12pt Medium

### Inputs (Text Form)
- Background: `Surface/Background/Background White`
- Border default: `Border/Text Form/Text Form Default`; active: `Border/Text Form/Text Form Active`
- Placeholder: `Text/Text Form/Text input Default`; value: `Text/Text Form/Text input Active`
- Label: `Text/Text Form/Label Form` 16pt Medium · Radius: `radius-md` (8) · Elevation: `shadow-xs`
- Error state *(proposed)*: border `Status/Error`, message text `Status/Error`, `aria-invalid`

### Map pin (Location)
- Default: surface `Background Light`, icon `Brand Icon Default`
- Active: darker brand fill, icon `Brand Icon Active`, `shadow`

### Snackbar
- Surface: dark neutral (Black 800/950), text White 14pt Medium, `shadow`, `radius-lg`

### Selected date / active fill
- Surface: `Surface/Background/Background Active`, text `White text`

## Rules

Always resolve a raw value through its semantic role here. If a needed role is missing (status colors, focus ring, hover), add a **new semantic token** rather than a raw hex. Prefer these tokens over primitives in all component and screen code.
