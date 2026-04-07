---
description: Create a new design for the current page while keeping specific positive elements the user identifies. Invoke with /ds:iterate to try a fresh approach without starting from zero.
argument-hint: "[what to keep from current design]"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "AskUserQuestion", "mcp__Claude_Preview__*"]
---


# /ds:iterate — New Design, Keep the Good Parts

Redesign the current page from scratch but preserve specific elements the user likes.

## Process

1. Read the current page component
2. Ask the user: "What do you want to KEEP from the current design?" (palette, specific animation, layout pattern, typography, a particular component)
3. Ask: "What do you want to CHANGE?" (or just "everything else")
4. Generate a new design that preserves the kept elements but reimagines everything else
5. Build, verify, present

## Rules

- The new design must feel genuinely different, not a minor tweak
- Kept elements should be adapted to work in the new context, not copy-pasted
- Run the same research phase as `/ds:dashboard` or `/ds:portfolio` for the new direction
- Still follow all design philosophy rules
