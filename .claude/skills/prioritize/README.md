# /prioritize

Decide what to build next by scoring features, ideas, and trade-offs against your actual context.

## How to use it

Type `/prioritize` followed by what you want to evaluate:

```
/prioritize search, notifications, dark mode
/prioritize should we build an API?
/prioritize mobile app vs progressive web app
/prioritize must-haves for search V1
```

It works in four modes:

- **Stack rank** ("rank these", "what should we build next?") -- scores a list of candidates and orders them
- **Opportunity assessment** ("should we build X?", "is this worth doing?") -- deep evaluation of one idea
- **Trade-off analysis** ("X vs Y", "which approach?") -- head-to-head comparison of alternatives
- **Scope cut** ("what's in V1?", "must-haves for launch", "cut scope") -- MoSCoW bucketing to decide what ships and what waits

## What you get

A scored analysis saved to `output/prioritization/` (e.g., `stack-rank-q2-features-2026-03-11.md`).

For stack rank, opportunity, and trade-off modes: each candidate is scored on user impact, strategic alignment, competitive pressure, effort, and confidence, with evidence cited from your context files.

For scope cut: features bucketed into Must/Should/Could/Won't with evidence-backed placement and trade-offs flagged.

## Tips

- Fill in context files first. Prioritization without `context/personas.md` and `context/company.md` is guessing, and the skill will tell you so.
- If you don't provide a list for stack rank, it scans pain points docs, interview themes, and meeting action items to assemble candidates.
- Effort scores require PM input. The skill asks rather than guesses.
- Pair with `/synthesize-interviews` to build the evidence base before prioritizing.
- Pair with `/prd` to spec out the top-ranked item or to define scope before a scope cut.
- Pair with `/analyze-competitors` if competitive pressure is a key factor.
- Say "finalize this" to move the analysis to `context/prioritization/`.
