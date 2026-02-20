---
name: competitive-analysis
description: Run a competitive analysis for a market or feature area.
argument-hint: [market-or-feature-area]
---

Run a competitive analysis for: $ARGUMENTS

Follow this workflow:

1. Read all files in `context/` — especially `context/competitors.md`, `context/product.md`, and `context/market.md`.
2. Read `template/competitive-analysis.md` as your starting structure.
3. Adapt the template — skip sections that don't apply, add sections that do.
4. Be opinionated: lead with a recommendation, not just a summary of findings.
5. Use specifics from context — actual product capabilities, known competitor strengths/weaknesses, real market dynamics.
6. If critical context is missing (e.g., no competitors listed), ask the user before guessing.
7. Save the output to `output/competitive-analysis-$ARGUMENTS.md` (use kebab-case for the filename).
