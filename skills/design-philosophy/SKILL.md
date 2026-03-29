---
name: Design Philosophy
description: This skill activates automatically during any web design task in the Design Studio plugin. It provides the foundational design philosophy, user taste preferences, and animation principles that govern all design decisions. Activates when building dashboards, portfolios, landing pages, or any web interface. Referenced by all other ds: skills.
version: 0.1.0
---

# Design Philosophy — Foundation

This skill carries the complete design philosophy and user taste profile for the Design Studio plugin. All design decisions — palette, typography, layout, motion, and component selection — derive from these principles.

## Core Design Identity

The design should feel like a **well-engineered instrument** — something between a CRT monitor, a scientific dashboard, and a luxury print publication. It communicates density and precision without clutter. It breathes through whitespace and opacity, not decoration.

Key words: **restrained, atmospheric, technical, alive, precise, elegant.**

## Full Design Philosophy

The complete design system specification lives in:
- **`references/web-design-philosophy.md`** — Full technical specification (colors, typography, layout, borders, animations, data viz, controls, responsive, special effects)

Load this reference when implementing any design. It contains exact CSS values, font stacks, color palettes, layout patterns, and animation keyframes.

## User Taste Profile

The user's preferences have been refined through extensive iteration. The critical rules:

### The Core Principle

**Animation is NOT the centerpiece. The PROJECT is the centerpiece. Animation SUPPLEMENTS the project.**

Animation plays three distinct roles depending on project type:

1. **Embodying the content** — The animation IS the subject (e.g., fractal trees growing on a page about fractal growth)
2. **Supplementing feelings** — The animation evokes the brand's emotional intent (e.g., gentle flowing particles for a luxury perfume)
3. **Giving urgency/functionality** — The animation signals the system is working (e.g., blinking indicators on a security dashboard)

Build the page ENTIRELY around the underlying project first. Then determine where motion adds value. Sometimes no animation is the right choice.

### What the User Loves

The detailed taste profile with ranked favorites lives in:
- **`references/taste-profile.md`** — Ranked tab favorites, what works and why, specific technique preferences, anti-patterns

Key highlights:
- Flow fields, particle trails, halftone dithering, L-system growth, ASCII rendering
- Dot-hero stippled numbers (gold/copper on dark backgrounds)
- Spring-animated cards and timeline nodes
- Breathing status indicators that signal system activity
- Interactive functionality (dropdowns, sorting, filtering)
- Strong, unique color identity per project
- Typography with personality — mixing cases, mixing serif/mono intentionally
- Each project having its own visual language

### What the User Hates

- Animation for animation's sake — movement that adds no meaning
- Excessive competing animations — too many things moving at once
- Generic SaaS aesthetics — rounded corners, gradient buttons, emoji, drop shadows
- AI slop — anything that looks generated rather than crafted by a human with taste
- Material/Bootstrap defaults, skeleton loaders, toast notifications with icons
- "Friendly" illustration styles, playful color palettes
- Light-mode treatments that break a dark theme

## How to Apply

1. **Determine the mode**: Is this immersive (dark, atmospheric) or informational (light, airy)? Pick palette accordingly.
2. **Set up CSS variables**: Define `--bg`, `--fg`, `--fg-dim`, `--fg-dark`, `--font-display`, `--font-mono` at `:root`.
3. **Establish zones**: Divide the page into distinct visual regions with clear borders or color shifts.
4. **Apply typography hierarchy**: Hero (display serif, massive) > Section heads (serif, medium) > Labels (mono, tiny, uppercase, dim) > Body (mono or serif, standard).
5. **Assess where motion adds value**: Does the project need urgency indicators? Emotional atmosphere? Content embodiment? Or just clean functionality?
6. **Apply the RIGHT technique**: Choose animation tools that serve the specific purpose, not the most impressive ones.
7. **Style controls last**: Buttons are inverted (fg background, bg text). Inputs are underline-only.

## Tech Stack

All Design Studio builds use **Vite + React**. Available libraries:
- **Framer Motion** — layout animations, spring physics, AnimatePresence, gestures
- **GSAP + ScrollTrigger** — scroll-pinned sections, scrubbed animations, timelines
- **Three.js / React Three Fiber** — 3D scenes, shader backgrounds, particle systems
- **Canvas 2D** — flow fields, dithering, reaction-diffusion, waveforms, generative art
- **Raw WebGL** — custom GLSL fragment shaders for GPU-computed visuals
- **Pure CSS** — clip-path morphing, mix-blend-mode, @property gradients, SVG stroke drawing

## Additional Resources

### Reference Files

- **`references/web-design-philosophy.md`** — Complete design system specification with exact CSS values
- **`references/taste-profile.md`** — User's ranked favorites and detailed preference analysis
- **`references/anti-patterns.md`** — Comprehensive list of what to avoid
- **`references/animation-techniques.md`** — Catalog of available animation techniques with when to use each
