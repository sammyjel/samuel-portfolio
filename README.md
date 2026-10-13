
# Samuel Ijeluola — Portfolio

Single-file, dependency-free personal site. Open `index.html` in any browser; there is no build step.

## Add your photo

The hero shows an "SI" monogram placeholder until a real photo exists. To swap it in:

1. Save your headshot as `assets/samuel.png` (or `.jpg` — update the `src` in `index.html` if so).
2. Best results: portrait crop, roughly 3:3.6 ratio, at least 800px wide, face in the upper third.
3. Reload. The placeholder disappears automatically once the file loads.

No other change is needed — the site detects whether the file exists at runtime.

## What's in here

| File | Purpose |
|---|---|
| `index.html` | The entire site — markup, styles and script |
| `netlify.toml` | Publish directory and security headers |
| `assets/` | Drop `samuel.png` here |

## Features

- **Flipbook CV** — a real 3D page-turn with spine shading and depth stacking. Click either half of the spread, drag horizontally, use ← / → keys, or jump with the page pips. Collapses to a single-page swipe deck under 820px.
- **Light / dark themes** — follows the OS by default, toggle persists to `localStorage`.
- **Reduced-motion support** — every animation is disabled when the OS asks for it.
- **Print stylesheet** — "Save as PDF" prints the CV pages only, one page per sheet, chrome stripped.
- Scroll progress bar, scroll-spy nav, section reveals, card spotlight, seamless stack marquee.

## Editing content

All CV copy lives in the `<section id="cv">` block, one `.leaf` per physical sheet. Each leaf has a
`.face.front` (right-hand page) and a `.face.back` (left-hand page, shown after the turn). Adding a
leaf requires no JS change — the page pips and bounds are derived from the DOM.

## Deploy

Already wired for Netlify (`publish = "."`). Any static host works: drop the folder in.
