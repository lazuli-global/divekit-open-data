# 🎨 Dive Kit Open - Color Theme

This site uses the Dive Kit editorial palette, shared with the main website
([divekit.app](https://divekit.app)), for a consistent experience across all platforms.

## Surfaces (paper)

- **Paper**: `#fbfaf7` - Warm off-white page background
- **Paper raised**: `#ffffff` - Card and content backgrounds
- **Paper tint**: `#f3f1ec` - Code blocks, table heads, suggestion boxes

## Text (ink)

- **Ink**: `#181a1c` - Primary text and headings
- **Ink secondary**: `#494d52` - Secondary text, code, blockquotes
- **Ink muted**: `#75797f` - De-emphasized text

## Rules (borders)

- **Rule**: `rgb(24 26 28 / 0.14)` - Hairline borders, dividers, table grid
- **Rule strong**: `rgb(24 26 28 / 0.45)` - Emphasized borders (table header underline, secondary buttons)

## Accent

- **Accent**: `#0369a1` - Dive Kit blue (links, buttons, headings accents)
- **Accent strong**: `#075985` - Hover states
- **Accent wash**: `rgb(3 105 161 / 0.06)` - Tinted backgrounds (blockquotes)

## Usage

The palette lives as CSS custom properties in `assets/site.css`, shared by
`index.html` and `404.html`. The `.dark` class on `<html>` swaps in the dark
"night reading" palette (paper `#14161a`, ink `#e7e4dd`, accent `#38bdf8`),
following the system theme unless `?theme=light|dark` is set, as on divekit.app.

- Headings: Source Serif 4; body: Inter; labels, tables and code: IBM Plex Mono
- Links and primary buttons: accent, accent strong on hover
- Cards and code: paper raised with a hairline rule
- Tables: mono uppercase heads over a strong rule, hairline rows

## Typography

- Headings: `'Source Serif 4', Georgia, 'Times New Roman', serif` (serif display, echoing the website)
- Body: system sans stack
- Code: system mono stack

Fonts are not self-hosted here; the serif stack falls back gracefully.

## Color Accessibility

Key combinations meet WCAG AA standards for contrast:

- `#0369a1` on `#ffffff`: ✅ 6.06:1 (AA)
- `#181a1c` on `#fbfaf7`: ✅ 15.9:1 (AAA)
- `#494d52` on `#ffffff`: ✅ 7.6:1 (AAA)

## Consistency

This palette mirrors the divekit.app website design system and the accent colors of the
Dive Kit mobile app (light theme accent `#0369a1`, dark theme accent `#38bdf8`; see
`divekit-app/src/lib/tamagui/themes.ts`). The previous brand blue `#0b95da` is retired
and should not be used in new material.
