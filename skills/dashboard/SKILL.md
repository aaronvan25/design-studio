---
name: dashboard
description: Build a professional, living dashboard or tool interface. Invoke with /ds:dashboard followed by a project title and optional description. Launches an interactive design flow, spawns a research agent team, creates a design plan, and builds a Vite + React page.
argument-hint: "<project title> [description]"
allowed-tools: ["Read", "Write", "Edit", "Bash", "Glob", "Grep", "Agent", "AskUserQuestion", "WebSearch", "WebFetch", "TodoWrite", "mcp__Claude_Preview__*"]
version: 0.1.0
---

# /ds:dashboard — Build a Living Dashboard

Build a professional dashboard or tool interface for a given project. The design is built entirely around the project's purpose, with animation that serves functionality.

## Workflow

### Step 1: Understand the Project

Parse the user's input for:
- **Project title** (required)
- **Project description** (optional — may come from conversation context)
- **Target audience** (who will use this dashboard?)
- **Core data/functionality** (what does it display or do?)

If any of these are unclear, use AskUserQuestion to gather them. Do NOT proceed without understanding what the dashboard is FOR.

### Step 2: Interactive Design Selection

Present choices one at a time using AskUserQuestion:

**A. Theme selection** — Present the 8 curated themes from the `theme-packages` skill. Let user pick one as a starting point, or choose "Custom" to build from scratch. Show palette colors and best-for description for each.

**B. Layout pattern** — Based on the project type, offer 2-3 layout options:
- 3-column with sidebar (like Cipherdeck) — for monitoring/operations
- Split pane with detail panel (like Forge Pipeline) — for list + detail views
- Full-width with bottom instrument panel (like Bloomberg) — for dense data
- Zoned panels with header stats (like Meridian Weather) — for sensor/metric dashboards

**C. Animation approach** — Ask what role animation should play:
- Urgency/functionality (live indicators, ticking numbers, scrolling feeds)
- Atmospheric (subtle background, breathing elements)
- Minimal (clean transitions only, no continuous animation)

**D. Key components** — Ask what data elements the dashboard needs (3-6 items):
- Live metrics/KPIs
- Data tables
- Charts/visualizations
- Feed/timeline
- Status grid
- Controls/filters

### Step 3: Research Phase

Launch an agent team for parallel research:

1. **Design Inspiration Researcher** — Search the web for modern dashboards in the project's domain. Use WebSearch/WebFetch (or Firecrawl MCP if available). Extract: color approaches, layout patterns, data visualization techniques.

2. **Architecture Planner** — Based on selections from Step 2, design the page structure: component hierarchy, data flow, layout grid.

3. **Anti-Pattern Reviewer** — Review the planned design against `references/anti-patterns.md` and the user's taste profile. Flag anything that might look like AI slop or violate preferences.

### Step 4: Present the Plan

Synthesize research into a concrete plan and present to user:
- Chosen palette with exact hex values
- Font selections
- Layout wireframe (describe zones and their content)
- Animation plan (what moves, what doesn't, and WHY)
- Component list with brief descriptions

Wait for user approval. Accept feedback and adjust before building.

### Step 5: Build

1. Check if user is in an existing Vite + React project (look for `package.json` with `vite` and `react`). If not, scaffold one.
2. Install any needed dependencies (framer-motion, gsap, three, etc.) based on the animation plan.
3. Create the page component as a single `.jsx` file.
4. Follow the design philosophy from `design-philosophy` skill:
   - Two-tone palette with opacity hierarchy
   - Proper typography scale (hero → section → label → body)
   - Sharp corners (no border-radius except for circular indicators)
   - Custom scrollbar styling
   - Proper ::selection colors
5. Start the dev server with preview tools and verify the build renders correctly.
6. Take a screenshot and present to the user.

### Step 6: Refinement

After presenting the initial build, inform the user of available refinement commands:
- `/ds:artify` — add artistic elements
- `/ds:animate` — add more motion
- `/ds:refine` — strip excess, clean up
- `/ds:iterate` — try a new direction keeping positives
- `/ds:nope` — full overhaul
- `/ds:blowup` — experimental redesign

## Key Rules

- Every pixel must serve the project's purpose
- Animation is a supplement, not the centerpiece
- The dashboard should look like it was designed by a human with strong opinions
- Test everything against the anti-pattern list before presenting
- If unsure about a design choice, err toward restraint over spectacle

## Reference Skills

- Load `design-philosophy` for full design system specification
- Load `theme-packages` for curated theme details
- Spawn agents from the `agents/` directory for research
