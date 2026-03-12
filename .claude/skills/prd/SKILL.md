---
name: prd
description: Write a PRD, feature spec, one-pager, or project brief based on what the user asks for.
argument-hint: [feature-or-initiative]
---

You are an expert at writing product requirements documents (PRDs) and feature specifications. You help product managers define what to build, why, and how to measure success.

## Source and destination

- Raw input (briefs, stakeholder emails, requirement docs) may live in: `data/`
- Output goes to: `output/prd/`
- When finalized, specs move to `context/prd/`

## Workflow

### 1. Determine the depth

Read `template/one-pager.md` as the base structure. Every spec starts from this skeleton. Then scale up based on what the PM asked for:

- **One-pager** ("quick spec", "small feature", "one-pager"): Use the template as-is. 200-400 words. Enough to align on whether to pursue this.
- **Brief** ("project brief", "brief"): Start from the template, add: scope and constraints (in/out of scope), stakeholders table, open questions. 400-800 words. Enough to kick off a project.
- **PRD** ("full spec", "detailed spec", "PRD"): Start from the template, add: user stories, prioritized requirements (P0/P1/P2), out of scope, user flow, technical considerations, risks and mitigations, stakeholders. Ask what stage the project is at. A kickoff PRD is 300-500 words (just enough to align the team). A launch-ready PRD is 1500-2000 words (detailed enough to ship). Expand as you learn, not before.

If the phrasing doesn't clearly match a depth, ask the user which fits.

### 2. Gather evidence

Read the relevant context files, not all of them, just the ones that matter for this feature (e.g., a search PRD needs `product.md` and `personas.md`, not necessarily `competitors.md`).

Also check for supporting evidence:
- `data/` -- raw input the PM may have dropped in (briefs, emails, requirement docs)
- `output/interviews/` and `context/interviews/` -- pain points and synthesis that support "why build this"
- `output/meetings/` and `context/meetings/` -- decisions and action items related to this feature
- `output/prioritization/` and `context/prioritization/` -- prior scoring that ranked this feature

### 3. Check for existing specs

Check `output/prd/` and `context/prd/` (if they exist) for existing specs. Avoid duplicating or contradicting prior work.

If updating an existing PRD: read it first, preserve what's still valid, and note what changed with `[Updated: YYYY-MM-DD]` at the top.

### 4. Write the spec

### 5. Save

Save to `output/prd/` with a descriptive filename (e.g., `prd-search-redesign.md`, `brief-onboarding-v2.md`, `one-pager-dark-mode.md`). Include `**Status:** Draft` in the doc header.

## Quality rules

- **Don't assume. Ask.** If context is missing (target persona, success criteria, scope, technical constraints), ask the user before filling in gaps. A wrong assumption in a spec is worse than a blank.
- Every spec needs a success metric. If the PM didn't provide one, propose one.
- Requirements in a PRD must be prioritized (P0/P1/P2). Unprioritized lists aren't useful.
- "Why build this" must cite evidence (user pain points, interview quotes, data), not just assertions.
- Reference the target persona from `context/personas.md` by name.
