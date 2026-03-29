---
name: artify
description: Add artistic elements, generative visuals, or atmospheric texture to an existing page. Invoke with /ds:artify to enhance a page with canvas art, halftone effects, flow fields, blend-mode layers, or other visual techniques that make the design feel more handcrafted.
argument-hint: "[optional: specific element or technique to add]"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "AskUserQuestion", "mcp__Claude_Preview__*"]
version: 0.1.0
---

# /ds:artify — Add Artistic Elements

Enhance an existing page with artistic, generative, or textural elements. This adds beauty without changing the page's core structure or purpose.

## Process

1. Read the current page component to understand its structure, palette, and content
2. Assess what artistic elements would complement the existing design
3. Ask the user what they want to add (or suggest 2-3 options based on the page's theme)
4. Implement the chosen elements
5. Verify with preview tools

## Technique Options

Consult `design-philosophy/references/animation-techniques.md` for the full catalog. Common artify additions:

- **Canvas background texture** — noise dot field, grain overlay, atmospheric gradient
- **Halftone/dithering effect** — apply to a section or hero area
- **Generated art piece** — canvas-rendered abstract artwork
- **Blend-mode atmospheric blobs** — soft color orbs behind content
- **Stencil/clip-path reveal effects** — on section transitions
- **Film grain or scanline overlay** — for retro/CRT aesthetic

## Rules

- Artistic elements must complement, not compete with, the existing content
- Use the page's existing palette — do not introduce new colors
- Verify the addition doesn't make labels unreadable or content inaccessible
- One or two additions per invocation — do not over-artify in one pass
