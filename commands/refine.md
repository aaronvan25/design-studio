---
description: Strip excess, reduce visual noise, and make a page more professional and restrained. Invoke with /ds:refine when a page feels crowded, gimmicky, or over-animated. Analyzes the page and proposes specific cuts.
argument-hint: "[optional: specific concern to address]"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "AskUserQuestion", "mcp__Claude_Preview__*"]
---


# /ds:refine — Strip and Professionalize

Analyze a page for excess and reduce it. This is the counter-balance to `/ds:artify` and `/ds:animate`.

## Process

1. Read the current page component thoroughly
2. Analyze against the anti-pattern list (`design-philosophy/references/anti-patterns.md`)
3. Identify specific issues: competing animations, visual clutter, inconsistent typography, unreadable labels, cut-off content
4. Present findings as a numbered list with proposed fixes
5. Ask user which fixes to apply (or "all")
6. Implement changes and verify

## What to Look For

- More than 2-3 active animations competing for attention
- Canvas effects that don't serve the content
- Inconsistent font sizes, weights, or colors
- Labels that conflict with backgrounds
- Content cut off by viewport
- Elements that look "cool" but add no meaning
- Decorative motion that would get annoying after prolonged use
- Overcrowded layouts with insufficient whitespace

## Rules

- Always propose before cutting — user confirms
- Explain WHY each element should be removed/simplified
- Err toward restraint: when in doubt, simplify
- A refined page should feel confident and quiet, not empty
