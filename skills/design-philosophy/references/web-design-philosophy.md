# Web Design Philosophy

You are building a web interface. Follow these design principles exactly. They define a specific aesthetic: technically precise, atmospheric, restrained, and alive. Every decision below is derived from real shipped work — not theory.

This document is adaptable. Match the principles to the project's subject matter. A weather app and a trading platform should feel different but share the same DNA.

---

## Core Identity

The design should feel like a **well-engineered instrument** — something between a CRT monitor, a scientific dashboard, and a luxury print publication. It communicates density and precision without clutter. It breathes through whitespace and opacity, not decoration.

Key words: **restrained, atmospheric, technical, alive, precise, elegant.**

Anti-patterns to avoid: rounded-corner card UIs, gradient buttons, emoji, playful color palettes, Material/Bootstrap defaults, generic SaaS aesthetics, skeleton loaders, toast notifications with icons, "friendly" illustration styles.

---

## Color

### Philosophy
Use a **two-tone foundation** with deliberate, sparing accent color. The palette should feel environmental — like the interface exists in a physical space with specific lighting conditions.

### Rules
1. Pick ONE dominant background color and ONE dominant text color. These two colors do 90% of the work.
2. Create hierarchy through **opacity variations** of the text color (100%, 50%, 20%), not by introducing new colors.
3. Accent colors are reserved for **status and severity only** — never for decoration.
4. Backgrounds should feel like a material: paper, screen phosphor, brushed metal — not a flat CSS color.

### Dark Mode Palettes (preferred for immersive/technical projects)
```
Deep green-black:  bg #0A1612  |  fg #D5E8D4  |  dim rgba(213,232,212,0.5)  |  dark rgba(213,232,212,0.2)
Deep purple-black: bg #1c121e  |  fg #ffea44  |  accents #ff2244, #a3cc46, #ff6622
Pure black tech:   bg #0a0a0c  |  fg #f4f4f4  |  accent #5CB8E4
Dark green nature: bg #0d1f0f  |  fg #f5f0e8  |  muted #8a9a8c
Near-black blue:   bg #030407  |  fg #FFFFFF  |  accent #4A88FF
```

### Light Mode Palettes (for print-like/archival projects)
```
Warm paper:   bg #f0f0f0  |  fg #121212  |  borders rgba(0,0,0,0.1)
Pure archive: bg #ffffff  |  fg #000000  |  accent #5CB8E4  |  gray #888
```

### Status Colors (universal)
```
Critical/error:  #FF4B4B or #ff2244
Warning:         #FFD700 or #ccae7a
Active/success:  inherit from fg color at full opacity
Inactive:        fg color at 20% opacity
```

### Applying to a New Project
Choose dark or light based on whether the interface is **immersive** (dark) or **informational/archival** (light). Then pick the palette closest to the project's subject matter. A weather app might use deep green-black. A financial tool might use pure black. A blog might use warm paper. Adjust the specific hex values to fit, but maintain the two-tone + opacity structure.

---

## Typography

### Philosophy
Typography does the heavy lifting. Use the **contrast between serif display type and monospace body type** to create sophistication. Monospace is not just for code — it is the voice of the system. Serif is the voice of the brand.

### Font Stacks
```
Display/Brand:  'Instrument Serif', serif  — OR —  system serif for lighter contexts
Monospace/Data: 'Space Mono', monospace  — OR —  'JetBrains Mono', 'SF Mono', 'Roboto Mono', monospace
Body/UI:        'Space Grotesk', 'Inter', -apple-system, sans-serif (use sparingly)
Impact/Hero:    Impact, 'Arial Black', sans-serif (for oversized dot-hero numerics only)
```

### Type Scale
```
Hero numbers:     clamp(4rem, 12vw, 14vw)  — massive, used once per page
Section titles:   2–3.5rem, display font, weight 400, no text-transform
Labels:           0.6–0.75rem, monospace, uppercase, letter-spacing 0.05–0.1em, opacity 0.5–0.7
Body:             0.85rem, monospace, letter-spacing 0.05em
Data values:      0.85–1rem, monospace, weight 400, letter-spacing -0.02em
Tiny metadata:    0.55–0.65rem, monospace, uppercase
```

### Rules
1. Labels are ALWAYS uppercase, monospace, small, with wide letter-spacing and reduced opacity.
2. Display headings are NEVER uppercase — use natural case with serif font at light weight (400).
3. Monospace for all data, values, timestamps, status text, navigation items, and body copy in technical interfaces.
4. Hero text should be unreasonably large — it's a visual element, not just text.
5. Letter-spacing: positive (0.05em+) on small uppercase text, slightly negative (-0.02 to -0.04em) on large display text.

---

## Layout

### Philosophy
Layouts are **zoned** — distinct visual regions with clear boundaries. Think satellite imagery panels, newspaper columns, or instrument clusters. Never a single scrolling column of cards.

### Patterns
```
Split pane:        grid-template-columns: 1fr 1fr  (50/50 for dashboard pairs)
Sidebar + content: grid-template-columns: 240px 1fr  (fixed sidebar, fluid content)
Asymmetric split:  grid-template-columns: 280px 1fr  (or 1fr 400px for config panels)
Data matrix:       grid-template-columns: repeat(4, 1fr)  (responsive to 2-col at 1024px)
Magazine columns:  column-count: 4  with break-inside: avoid  (for archival/blog content)
```

### Rules
1. Use CSS Grid for page-level structure, flexbox for component internals.
2. Full viewport height (`100vh`) for primary layouts. Overflow is controlled per-panel, not on the page.
3. Gaps should be generous: 32–64px between major sections, 8–16px within components.
4. Sticky headers within scrollable regions (position: sticky, top: 0, background matching zone).
5. Container max-widths: 1200–1440px for content, no max-width for immersive/full-bleed layouts.
6. Padding: 2–4rem on major sections, 1–1.5rem on compact panels.

### Zone Transitions
When moving between dark and light zones (or any two distinct visual regions), use a **transition zone** — a gradient mask with a dot-pattern overlay that fades between them. This is a signature technique:
```css
.zone-transition {
  height: 180px;
  position: relative;
}
.zone-transition::before {
  /* gradient mask from dark to transparent */
  mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 0%, rgba(0,0,0,0) 10%);
}
.zone-transition::after {
  /* dot pattern that fades out */
  background: radial-gradient(circle, var(--fg) 1.5px, transparent 1.5px);
  background-size: 6px 6px;
  mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 0%, rgba(0,0,0,0) 90%);
}
```

---

## Borders, Backgrounds & Depth

### Philosophy
**Flat with intent.** No drop shadows for depth. No card elevations. Depth comes from zone coloring, opacity layers, and subtle inset shadows only on physical/skeuomorphic elements (dials, screens, buttons that look like hardware).

### Rules
1. Borders: `1px solid` using fg color at 10–20% opacity. Use dotted borders (`1px dotted`) for data row separators.
2. Border-radius: **zero** on almost everything. Sharp corners are the default. Use `border-radius: 50%` only for circular indicators/nodes. Use small radius (4–12px) only for physical device bezels.
3. Backgrounds: transparent or zone color. Never card-like raised backgrounds. Hover states use `rgba(fg, 0.02–0.03)` — barely visible.
4. Scrollbars: custom styled — 4px width, transparent track, fg at 20% opacity for thumb.
5. Selection: invert colors — `::selection { background: var(--fg); color: var(--bg); }`

### Atmospheric Backgrounds
For immersive projects, layer subtle effects:
```css
/* Radial spotlight */
background-image: radial-gradient(circle at 15% 15%, var(--bg-alt) 0%, var(--bg) 60%);
background-attachment: fixed;

/* Dot texture */
background-image: radial-gradient(circle at center, rgba(fg, 0.04) 1px, transparent 1px);
background-size: 8px 8px;
```

---

## Animations & Motion

### Philosophy
Motion should make the interface feel **alive, not animated.** Things breathe, pulse, and rotate — they don't bounce, slide, or pop. Think vital signs monitor, not mobile app.

### Standard Transitions
```css
/* Page entrance */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(5px); }
  to { opacity: 1; transform: translateY(0); }
}
animation: fadeIn 0.4s ease-out;

/* Staggered list entrance */
animation-delay: calc(var(--index) * 0.1s);

/* Hover transitions */
transition: opacity 0.2s ease;  /* or background 0.2s ease */
```

### Living Indicators
```css
/* Pulse (for active/live nodes) */
@keyframes pulse {
  0% { transform: scale(1); opacity: 0.4; }
  50% { transform: scale(3); opacity: 0; }
  100% { transform: scale(1); opacity: 0; }
}

/* Spinner (for in-progress/loading) */
@keyframes spin {
  to { transform: rotate(360deg); }
}
/* Applied to a quarter-circle border element, 3–4s linear infinite */

/* Blink (for critical alerts or cursor) */
@keyframes blink {
  0%, 49% { opacity: 1; }
  50%, 100% { opacity: 0; }
}
```

### Rules
1. Page elements fade in with slight upward movement (5px translateY). Duration: 0.3–0.4s.
2. List items stagger their entrance by 0.1s per index.
3. Hover effects are opacity-only or near-invisible background tint. Never scale, rotate, or color-shift on hover.
4. Continuous animations (pulse, spin, breathe) are for status indicators only — never decorative.
5. Sensor/data grids use `transition: opacity 0.4s ease` on individual nodes to create organic breathing patterns.
6. Easing: `cubic-bezier(0.16, 1, 0.3, 1)` for entrances (fast start, gentle settle). `ease-out` for simple transitions.

---

## Data Visualization

### Philosophy
Data is shown through **typographic scale, opacity mapping, and texture** — not chart libraries. When you need a bar, build it from a `div`. When you need a graph, build it from characters.

### Techniques

**Dot-Hero Numbers** — The signature large-number technique:
```css
.dot-hero {
  font-size: 14vw;
  font-family: Impact, 'Arial Black', sans-serif;
  font-weight: 900;
  line-height: 0.8;
  color: transparent;
  background-image: radial-gradient(circle at center, var(--fg) 2px, transparent 2px);
  background-size: 8px 8px;
  -webkit-background-clip: text;
  background-clip: text;
}
```

**Spark Bars** — Thin striped progress indicators:
```css
.spark-bar {
  height: 4px;
  background: var(--fg);
  background-image: repeating-linear-gradient(
    45deg, transparent, transparent 2px, var(--bg) 2px, var(--bg) 4px
  );
}
```

**Sensor Grids** — Opacity-mapped node matrices:
```css
.sensor-grid { grid-template-columns: repeat(32, 1fr); gap: 2px; }
.sensor-node {
  aspect-ratio: 1;
  border-radius: 50%;
  background: var(--fg);
  opacity: 0.1; /* dynamically set 0.1–1.0 */
  transition: opacity 0.4s ease;
}
```

**ASCII Visualization** — Character-based rendering for immersive data:
- Use canvas or pre-formatted monospace text
- Characters by density: `@ O & Q c ~ = - .` (space)
- Apply `filter: drop-shadow(0 0 5px rgba(fg, 0.3))` for glow
- Use `image-rendering: pixelated` on canvas elements

**Timeline/Ledger** — Vertical dotted line with status nodes:
- Dotted `border-left` on a pseudo-element
- Circular nodes at each entry: solid (complete), quarter-border spinning (in-progress), light border (planned)
- Staggered fade-in on entries

---

## Interactive Elements

### Philosophy
Controls should feel like **instrument panel switches** — minimal, precise, clearly stated. Not friendly, not playful.

### Buttons
```css
/* Primary action */
.btn-primary {
  background: var(--fg);
  color: var(--bg);
  border: none;
  padding: 0.75rem 2rem;
  font-family: var(--font-mono);
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  cursor: pointer;
  transition: opacity 0.2s;
}
.btn-primary:hover { opacity: 0.9; }
.btn-primary:disabled { opacity: 0.5; cursor: not-allowed; }

/* Secondary/ghost */
.btn-secondary {
  background: transparent;
  color: var(--fg-dim);
  border: none;
  font-family: var(--font-mono);
  text-transform: uppercase;
  font-size: 0.7rem;
}
```

### Inputs
```css
.input {
  background: transparent;
  border: none;
  border-bottom: 1px solid var(--fg-dark);
  color: var(--fg);
  font-family: var(--font-mono);
  padding: 0.5rem 0;
  outline: none;
  transition: border-color 0.3s ease;
}
.input:focus { border-bottom-color: var(--fg); }
.input::placeholder { color: var(--fg-dark); }
```

### Toggle Switches
Square, not rounded. 40x20px with 1px border. Active state shows a small filled square inside, not a sliding circle.

### Pills/Tags
```css
.pill {
  display: inline-block;
  padding: 2px 8px;
  border: 1px solid var(--fg);
  font-family: var(--font-mono);
  font-size: 0.65rem;
  text-transform: uppercase;
  cursor: pointer;
  transition: all 0.15s ease;
}
.pill.active {
  background: var(--fg);
  color: var(--bg);
}
```

### Sliders
Custom styled: 2px track, 12x12px square thumb (no border-radius), fg color.

### Navigation
```css
.nav-item {
  color: var(--fg-dim);
  font-family: var(--font-mono);
  font-size: 0.8rem;
  text-transform: uppercase;
  transition: color 0.2s;
}
.nav-item::before {
  content: '>';
  opacity: 0;
  transform: translateX(-5px);
  transition: all 0.2s;
}
.nav-item:hover { color: var(--fg); }
.nav-item:hover::before { opacity: 1; transform: translateX(0); }
```

---

## Special Effects (use sparingly)

### CRT Scanlines
```css
.scanlines {
  background-image: linear-gradient(
    to bottom, transparent 50%, rgba(fg, 0.01–0.03) 50%
  );
  background-size: 100% 4px;
  pointer-events: none;
}
```

### CRT RGB Chromatic Aberration (modals/overlays only)
```css
.crt-overlay::before {
  background:
    linear-gradient(rgba(18,16,16,0) 50%, rgba(0,0,0,0.1) 50%),
    linear-gradient(90deg, rgba(255,0,0,0.03), rgba(0,255,0,0.01), rgba(0,0,255,0.03));
  background-size: 100% 2px, 3px 100%;
}
```

### Crosshair Overlay
Two 1px lines (horizontal + vertical) crossing at center of a visualization panel. Color: fg at 20% opacity.

### Glow Effects
`box-shadow: 0 0 10px 2px rgba(fg, 0.2)` on active nodes. `text-shadow: 0 0 6px rgba(fg, 0.3)` on phosphor-style text. `filter: drop-shadow(0 0 5px rgba(fg, 0.3))` on ASCII/canvas elements.

### WebGL/Canvas Backgrounds
For hero sections or immersive pages, use shader-based backgrounds:
- Perlin/Simplex noise for organic movement
- Sine/cosine wave patterns for rhythmic motion
- Ordered dithering (Bayer matrix) for retro texture
- Mouse-tracking uniforms for subtle interactivity
- Always use `image-rendering: pixelated` on canvas elements

---

## Cursor
For immersive/technical interfaces, override the cursor globally:
```css
*, *::before, *::after { cursor: crosshair; }
```
For lighter/archival interfaces, use default cursor.

---

## Responsive Behavior

### Breakpoints
```
1024px: Collapse 4-col grids to 2-col. Collapse sidebar layouts to single column.
600px:  Single column everything. Reduce padding to 24px. Scale hero text down.
```

### Rules
1. Use `clamp()` for fluid font sizing on hero/display text.
2. Sidebar becomes top-bar or collapses on mobile.
3. Data matrices go from 4-col to 2-col to 1-col.
4. Maintain the aesthetic at every breakpoint — don't fall back to generic mobile patterns.

---

## How to Apply This to Any Project

1. **Determine the mode**: Is this immersive (dark, atmospheric, full-viewport) or informational (light, airy, scrollable)? Pick your palette accordingly.
2. **Set up CSS variables**: Define `--bg`, `--fg`, `--fg-dim`, `--fg-dark`, `--font-display`, `--font-mono` at `:root`.
3. **Establish zones**: Divide the page into distinct visual regions with clear borders or color shifts between them.
4. **Apply typography hierarchy**: Hero (display serif, massive) > Section heads (display serif, medium) > Labels (mono, tiny, uppercase, dim) > Body (mono, standard).
5. **Build data displays**: Use opacity mapping, spark bars, dot-hero numbers, and sensor grids — not chart libraries.
6. **Add life**: Subtle breathing animations on data nodes, staggered fade-ins on lists, pulse on active indicators.
7. **Layer atmosphere**: Add scanlines, dot textures, or radial gradients only if the project is immersive. Skip for archival/light mode.
8. **Style controls last**: Buttons are inverted (fg background, bg text). Inputs are underline-only. Everything is monospace and uppercase.

The goal is an interface that looks like it was designed by someone who builds synthesizers and reads Edward Tufte. Dense with information, light on decoration, alive with subtle motion.
