---
name: inspo
description: Ingest a design inspiration from a URL or screenshot. Invoke with /ds:inspo followed by a URL or after providing a screenshot. Extracts design elements the user likes and adds them to the design philosophy and technique catalog.
argument-hint: "<URL or 'screenshot'>"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "AskUserQuestion", "WebSearch", "WebFetch", "mcp__Claude_Preview__*"]
version: 0.1.0
---

# /ds:inspo — Ingest Design Inspiration

Extract design elements from a website or screenshot and add them to the design system.

## Process

### If URL provided:
1. Fetch the page with WebFetch (or Firecrawl MCP if available for full rendering)
2. Analyze: palette, typography, layout structure, animation techniques, overall aesthetic
3. Present findings to user as a structured breakdown

### If screenshot provided:
1. Read the screenshot image
2. Analyze visible: colors, fonts, layout, spacing, visual techniques
3. Present findings to user

### Interactive Extraction:
4. Ask user: "What specifically do you like about this design?" with options:
   - Color palette / specific colors
   - Typography choices
   - Layout pattern
   - Animation / motion technique
   - Overall vibe / feeling
   - Specific component or element
5. For each identified element, extract it into a structured format
6. Ask: "Should I add this to your design philosophy?"
7. If yes, append to the appropriate reference file:
   - New palette → add to `theme-packages` as a new theme entry
   - New technique → add to `animation-techniques.md`
   - New anti-pattern → add to `anti-patterns.md`
   - New preference → add to `taste-profile.md`

## Rules

- Never overwrite existing preferences — only append
- Always confirm before adding to the design system
- Extract specific, actionable design elements, not vague descriptions
- If a URL is inaccessible, ask user to provide a screenshot instead
