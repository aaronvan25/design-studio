---
description: Add domain-appropriate motion to specific parts of an existing page. Invoke with /ds:animate to bring elements alive with breathing indicators, ticking numbers, waveforms, spring physics, or other purposeful motion.
argument-hint: "[optional: which section or element to animate]"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "AskUserQuestion", "mcp__Claude_Preview__*"]
---


# /ds:animate — Add Purposeful Motion

Add animation to specific parts of an existing page. Every addition must serve a purpose — urgency, atmosphere, or content embodiment.

## Process

1. Read the current page to understand its content and purpose
2. Identify which elements would benefit from motion and WHY
3. Present options to the user, explaining the purpose of each
4. Implement the chosen animations
5. Verify with preview tools — ensure nothing competes or overwhelms

## Before Adding Motion, Ask

- Does this page NEED more motion? If it already has competing animations, `/ds:refine` may be more appropriate.
- What purpose does the motion serve? (urgency, atmosphere, embodiment, readability)
- Will this motion still be pleasant after staring at it for an hour?

## Rules

- Consult `design-philosophy/references/animation-techniques.md` for the technique catalog
- Match the technique to the PURPOSE, not to what looks coolest
- Maximum 2-3 new animated elements per invocation
- Always check: does the new motion conflict with existing motion?
- After adding, run the anti-pattern check: is this animation for its own sake?
