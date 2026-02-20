---
name: stakeholder-update
description: Write a stakeholder update for a project or initiative.
argument-hint: [project-name]
---

Write a stakeholder update for: $ARGUMENTS

Follow this workflow:

1. Read all files in `context/` for company and product grounding.
2. Read `template/stakeholder-update.md` as your starting structure.
3. Check `output/` for any recent artifacts (PRDs, analyses) related to the project — reference them for status and metrics.
4. Adapt the template — skip sections that don't apply, add sections that do.
5. Write for the audience: concise, story-driven, focused on what stakeholders need to know and decide.
6. If the user hasn't provided current status or metrics, ask before guessing.
7. Save the output to `output/stakeholder-update-$ARGUMENTS.md` (use kebab-case for the filename).
