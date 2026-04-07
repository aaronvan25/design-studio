---
name: portfolio
description: Build a professional portfolio, landing page, or showcase site. Invoke with /ds:portfolio followed by a project title and optional description. Launches an interactive design flow with theme selection, spawns research agents, and builds a Vite + React page focused on visual storytelling rather than data density.
argument-hint: "<project title> [description]"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "Agent", "AskUserQuestion", "WebSearch", "WebFetch", "TodoWrite", "mcp__Claude_Preview__*"]
version: 0.1.0
---

# /ds:portfolio — Build a Portfolio or Landing Page

Build a showcase site, portfolio, or landing page. Unlike dashboards (which prioritize data density and functionality), portfolios prioritize visual storytelling, atmosphere, and editorial layout.

## Workflow

Follow the same workflow as `/ds:dashboard` — including **Step 4b (Choose Build Location)** — with these differences:

### Step 2 Differences: Design Selection

**Layout patterns to offer:**
- Full-viewport vertical scroll with alternating sections (like Drift, Praxis)
- Horizontal scroll gallery (like Cooperage barrel aisle)
- Magazine columns with card grid (like Archivum)
- Single centered column with massive whitespace (like Stillwater, Kinetic)
- Asymmetric split: large visual + narrow text (like Vesper)

**Animation approach options:**
- Atmospheric (flow fields, blend-mode blobs, ambient noise)
- Content-embodying (the animation IS the subject matter)
- Editorial (scroll reveals, stencil cuts, staggered entries)
- Minimal/typographic (text drifts, letters expand, breathing lines)

**Additional question: Generated art**
If the portfolio needs visual placeholders, offer to generate canvas-based artwork:
- Dot-matrix (warm reds/oranges — like Praxis Ignition Point)
- Spray splashes (multi-color radial — like Praxis Chromatic Discharge)
- Organic noise field (blues/teals)
- Geometric opacity grid
- Layered stripe collage
- Watercolor washes (like Stillwater)

### Step 5 Differences: Build

- Prioritize typography and whitespace over information density
- Use larger font sizes for display text
- Generous padding between sections (100px+)
- Content should feel like unwrapping, not scrolling
- If generating art, create unique canvas components per piece

## Key Rules

- Portfolio pages are about FEELING, not FUNCTION
- The design should match the subject's personality — a Banksy portfolio feels different from a luxury brand
- Motion supplements the emotional intent of the brand/artist/project
- Every design choice should answer: "Does this serve the story being told?"
- Avoid dashboard patterns (grids, tables, stat rows) unless the portfolio IS about data

## Reference Skills

Same as `/ds:dashboard` — load `design-philosophy` and `theme-packages`.
