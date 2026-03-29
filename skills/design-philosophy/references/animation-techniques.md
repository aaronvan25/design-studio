# Animation Techniques Catalog

A catalog of available techniques organized by WHEN to use them, not what they are.

## For Urgency / "System Is Active" (Dashboards, Monitors)

### Breathing Status Indicators
- Small dot that pulses opacity or box-shadow on a slow cycle
- Signals: feed is live, system is connected
- CSS keyframes, 2-3s cycle

### Blinking Alert Dots
- Square or circle that blinks on/off with `step-end` timing
- Signals: critical alert, requires attention
- CSS keyframes, 1-1.5s cycle

### Scrolling Ticker Tape
- Horizontal text that scrolls continuously via CSS transform
- Signals: live market data flowing
- setInterval updating translateX

### Ticking Numbers
- Values that update via setInterval
- Signals: data is live and changing
- React state updates, fontVariantNumeric: 'tabular-nums'

### Spinning Progress Nodes
- Quarter-circle border rotating on in-progress items
- Signals: task is actively running
- CSS keyframes rotate, 2-3s linear infinite

### Sensor Grid / Threat Matrix
- Grid of dots/squares with opacity mapped to live values
- Color changes on threshold (green/yellow/red)
- Signals: monitoring network of sensors/nodes
- React state with setInterval, CSS transitions

## For Feeling / Atmosphere (Brands, Portfolios, Landing Pages)

### Flow Field Particle Trails
- Thousands of particles following noise-based vector field
- Semi-transparent strokes that accumulate into luminous streams
- Canvas 2D, requestAnimationFrame, slow fade (rgba bg overlay)
- Best for: luxury brands, organic/natural themes

### Mix-Blend-Mode Color Blobs
- Large blurred circles with `mix-blend-mode: screen`
- Slowly orbit, producing new colors at intersections
- Pure CSS animation, no canvas needed
- Best for: atmospheric hero sections

### Halftone / Ordered Dithering
- Bayer matrix applied to live animated gradients
- Creates print-like, artistic texture in real-time
- Canvas 2D, per-pixel computation
- Best for: artistic/editorial projects

### Stencil Clip-Path Reveals
- Content reveals left-to-right via `clip-path: inset()` transition
- Like spray paint through a stencil
- Pure CSS transition
- Best for: street art, raw/urban projects

### Slow Scroll Reveals
- Sections fade in with slight translateY as they enter viewport
- IntersectionObserver or Framer Motion
- Best for: reports, portfolios, long-form content

## For Content Embodiment (When the Animation IS the Subject)

### L-System Fractal Growth
- Branching structures that animate their growth from seed
- Different rule sets produce different tree/plant shapes
- Canvas 2D, pre-computed segments, progress animation
- Best for: anything about growth, nature, biology, branching

### Reaction-Diffusion (Gray-Scott)
- Organic coral/maze/spot patterns that evolve in real-time
- Different feed/kill parameters produce different pattern families
- Canvas 2D, per-pixel Laplacian computation
- Best for: biology, mycology, organic chemistry

### Boids Flocking
- Agents that school/flock from 3 simple rules
- Emergent behavior that looks eerily lifelike
- Canvas 2D with spatial hashing
- Best for: anything about swarms, collective behavior, emergence

### Voronoi Tessellation
- Organic cell-like patterns with glowing edges
- Seed points move, cells shift
- Canvas 2D, per-pixel distance computation
- Best for: biology, cellular structures, networks

### Waveform Canvas
- Sine waves with amplitude/frequency mapped to data
- Multiple layers with different colors
- Canvas 2D, requestAnimationFrame
- Best for: audio, signal processing, frequency analysis

## For Readability Enhancement (Reports, Archives, Blogs)

### Expandable Cards
- Click to expand additional content (dropdown within a card)
- Page shifts to accommodate new content
- React state toggle, CSS transition on height
- Best for: archives, catalogs, research findings

### Tag/Filter Sorting
- Filter pills that reorder/filter content
- Active pill gets inverted styling
- React state filter, CSS transition on layout
- Best for: catalogs, archives, research databases

### Reading Progress Bar
- Thin bar at top that fills as user scrolls
- Scroll event listener or CSS scroll-timeline
- Best for: long-form reports, articles

### Spring-Animated Cards (Framer Motion)
- Cards spring in with staggered delay
- AnimatePresence for mount/unmount
- Best for: feeds, lists, search results

## For Finance Specifically

### Dot-Hero Stippled Numbers
- Large numbers rendered with radial-gradient dot pattern clipped to text
- Gold/copper on dark backgrounds
- CSS background-clip: text
- Best for: key metrics, hero statistics

### Heat-Mapped Cells
- Background color intensity maps to value magnitude
- Green for positive, red for negative, opacity for strength
- CSS rgba with computed alpha
- Best for: position grids, comparable tables, sector maps

### Candlestick with Glow
- Canvas-rendered OHLC candles with soft glow halos and grain texture
- Green hollow for bullish, red filled for bearish
- Canvas 2D with globalAlpha layering
- Best for: price charts, trading interfaces

### ASCII Rendering
- Monospace text characters mapped to data density
- Characters by density: `@ O & Q c ~ = - .` (space)
- Filter: drop-shadow for glow effect
- Best for: retro/terminal-style displays, unique aesthetic
