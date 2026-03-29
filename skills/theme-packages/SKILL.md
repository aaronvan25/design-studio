---
name: Theme Packages
description: This skill provides 8 curated theme packages extracted from the Design Workshop. Each theme bundles a palette, font stack, layout pattern, and recommended animation techniques. Referenced when the user selects a theme during /ds:dashboard or /ds:portfolio, or when needing inspiration for color/font/layout decisions.
version: 0.1.0
---

# Theme Packages — Curated Design Systems

Eight complete theme packages extracted from the user's favorite Design Workshop tabs. Each theme is a self-contained design system with palette, typography, layout pattern, and domain-appropriate animation techniques.

## Available Themes

### 1. Drift
**Domain:** Luxury / Brand / Atmospheric
**Palette:** Deep black (#050505), warm cream (#f0e8d8), rose (#c4748a), amber (#d4a060), violet (#8a6aaa)
**Fonts:** Didot/Bodoni for display (weight 300), no monospace
**Layout:** Full-viewport vertical scroll, alternating image/text sections
**Animations:** Flow field particle trails (canvas), mix-blend-mode blobs (CSS), slow scroll reveals
**Best for:** Luxury brands, perfume, fashion, high-end products

### 2. Cipherdeck
**Domain:** Security / Dashboard / Operations
**Palette:** Near-black blue (#030407), white (#FFFFFF), electric blue accent (#4A88FF), red (#FF4B4B), green (#4BFF7B)
**Fonts:** Space Mono for everything, labels uppercase with wide letter-spacing
**Layout:** 3-column with header stats bar, sidebar feed, main content
**Animations:** Breathing sensor grid, blinking alert indicators, live status dots, protocol bars
**Best for:** Security dashboards, operations centers, monitoring tools

### 3. Halftone
**Domain:** Artistic / Print / Editorial
**Palette:** Warm paper (#f0ece0), dark ink (#1a1a1e), accent red (#c44830)
**Fonts:** Instrument Serif for headings, Space Mono for technical labels
**Layout:** 3-column grid showing technique variations side by side
**Animations:** Bayer ordered dithering, halftone dot rendering, color dithering — all on live animated gradients
**Best for:** Art/design projects, print-inspired layouts, risograph aesthetic

### 4. Arboretum
**Domain:** Nature / Growth / Scientific
**Palette:** Deep forest (#0a0e08), pale lichen (#c8d8b8), warm brown (#8a6a40), green accent (#6a9a4a)
**Fonts:** Space Mono for labels, Instrument Serif for names
**Layout:** 2x2 grid of equal panels, each containing one visualization
**Animations:** L-system fractal tree growth with color gradient (brown trunk → green tips)
**Best for:** Biology, nature, growth-themed projects, scientific visualization

### 5. Loom
**Domain:** Craft / Textile / Interactive Tool
**Palette:** Soft indigo (#0d0f1a), warm cream (#f0e8d8), indigo accent (#4a5296), rust (#a0522d), sage (#6b7c5e), ochre (#c4973b)
**Fonts:** Instrument Serif for pattern names, Space Mono for data
**Layout:** Full-page centered — the product (weave grid) IS the page, side stats panel
**Animations:** Weave grid advances row-by-row, thread imperfections appear, tension values tick
**Best for:** Craft tools, interactive makers, design tools, configuration interfaces

### 6. Synthwave Audio
**Domain:** Music / Audio / Retro-Tech
**Palette:** Deep purple-black (#1c121e), electric yellow (#ffea44), red (#ff2244), green (#a3cc46), orange (#ff6622)
**Fonts:** Space Mono everywhere, track names in natural case (NOT all-caps)
**Layout:** Sidebar (280px) + main (waveform + spectrum), bottom transport bar
**Animations:** Canvas waveform, frequency spectrum bars (100ms refresh), playing indicator bars, scanline overlay
**Best for:** Audio/music tools, retro-tech dashboards, media players

### 7. Forge Pipeline
**Domain:** DevOps / CI-CD / Engineering
**Palette:** Pure black tech (#0a0a0c), white (#f4f4f4), blue accent (#5CB8E4), red (#FF4B4B), green (#4BFF7B), yellow (#FFD700)
**Fonts:** Space Mono, Instrument Serif for build IDs
**Layout:** 3-column: build list (320px), pipeline detail (1fr), environments (300px)
**Animations:** Spinning progress nodes on running stages, dot-hero status words, build status color bars
**Best for:** CI/CD dashboards, deployment tools, engineering operations

### 8. Praxis
**Domain:** Art Portfolio / Gallery / Showcase
**Palette:** Gallery black (#0a0a0a), warm off-white (#f0ece4)
**Fonts:** Instrument Serif massive for hero, Space Mono for medium/dimensions, italic for descriptions
**Layout:** Full-viewport vertical scroll, alternating artwork/placard sides per section
**Animations:** Canvas-generated abstract art (5 different algorithms), scroll-triggered reveals, slow ambient hero noise
**Art generation:** Dot-matrix (reds/oranges), spray splashes (multi-color), oil noise field (blues/teals), geometric grid (on cream), layered stripes (mixed media)
**Best for:** Art portfolios, gallery sites, creative showcases

## How to Use

When a user is choosing a theme during `/ds:dashboard` or `/ds:portfolio`:

1. Present the 8 themes with their domain, palette colors, and best-for descriptions
2. Let the user select one as a starting point
3. The theme provides defaults for palette, fonts, layout, and animation approach
4. These can be customized during the interactive design flow
5. Load the specific theme's detailed reference from `themes/` for exact values

## Theme Reference Files

Detailed CSS values and component patterns for each theme:
- **`themes/drift.md`**
- **`themes/cipherdeck.md`**
- **`themes/halftone.md`**
- **`themes/arboretum.md`**
- **`themes/loom.md`**
- **`themes/synthwave.md`**
- **`themes/forge.md`**
- **`themes/praxis.md`**
