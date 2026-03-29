# Design Studio (ds)

A Claude Code plugin that turns project descriptions into professionally designed web pages using a personal design philosophy, curated theme packages, and advanced animation techniques.

## Commands

| Command | Purpose |
|---------|---------|
| `/ds:dashboard` | Build a functional dashboard or tool interface |
| `/ds:portfolio` | Build a portfolio, landing page, or showcase site |
| `/ds:artify` | Add artistic elements and generative visuals |
| `/ds:animate` | Add domain-appropriate motion to specific elements |
| `/ds:refine` | Strip excess, reduce visual noise, professionalize |
| `/ds:iterate` | New design keeping identified positive elements |
| `/ds:nope` | Full design overhaul — start from scratch |
| `/ds:blowup` | Experimental wild redesign — no safety net |
| `/ds:inspo` | Ingest design inspiration from a URL or screenshot |

## Tech Stack

All builds use **Vite + React** with access to:
- Framer Motion (spring physics, layout animation)
- GSAP + ScrollTrigger (scroll-driven animation)
- Three.js / React Three Fiber (3D, shaders)
- Canvas 2D (generative art, flow fields, dithering)
- Raw WebGL (custom GLSL shaders)

## Theme Packages

8 curated themes extracted from the Design Workshop:
Drift, Cipherdeck, Halftone, Arboretum, Loom, Synthwave Audio, Forge Pipeline, Praxis

## Optional: Firecrawl MCP

For deeper web scraping during design research, set:
```
export FIRECRAWL_API_KEY=your_key_here
```

Without it, the plugin gracefully falls back to WebSearch/WebFetch.

## Installation

```bash
claude --plugin-dir /Users/aaronfriedman/.claude/plugins/ds
```
