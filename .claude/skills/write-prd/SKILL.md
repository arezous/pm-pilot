---
name: write-prd
description: Write a product requirements document for a feature or initiative.
argument-hint: [feature-name]
---

Write a PRD for: $ARGUMENTS

Follow this workflow:

1. Read all files in `context/` to ground yourself in the company, product, competitors, personas, and market.
2. Read `template/prd.md` as your starting structure.
3. Adapt the template — skip sections that don't apply, add sections that do.
4. Be opinionated: state your recommendation, then support it. Don't write generic filler.
5. Reference specifics from the context files — company metrics, persona pain points, competitive gaps.
6. If critical context is missing, ask the user before guessing.
7. Save the output to `output/prd-$ARGUMENTS.md` (use kebab-case for the filename).
