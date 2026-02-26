# /write-spec

Write a PRD, one-pager, or project brief for a feature or initiative.

## How to use it

Type `/write-spec` followed by what you want to spec out:

```
/write-spec dark mode
/write-spec onboarding redesign
```

You can ask for a specific format ("write a one-pager for...", "full PRD for...") or let it ask. It picks from three templates based on scope:

- **One-pager** — small features, quick alignment
- **Brief** — project-level overview
- **PRD** — detailed spec, sized to project stage (kickoff vs. launch-ready)

## What you get

A markdown document saved to `output/specs/` (e.g., `prd-search-redesign.md`, `one-pager-dark-mode.md`). It pulls from your context files and checks for existing specs to avoid contradictions.

## Tips

- For PRDs, it asks what stage you're at. A kickoff PRD is 300-500 words. A launch-ready PRD is 1500-2000 words.
- Fill in `context/product.md` and `context/personas.md` first for better results.
- Pair with `/synthesize-interviews` to ground specs in real user evidence.
- Say "finalize this" to move a spec to `context/specs/`.
