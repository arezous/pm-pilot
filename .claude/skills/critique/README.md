# /critique

Pressure-test any document against your product context before sharing it.

## How to use it

Type `/critique` followed by what you want reviewed:

```
/critique the search PRD
/critique output/prd/prd-onboarding-v2.md
/critique our positioning
```

Or just type `/critique` and paste the document.

## What you get

A structured critique covering: what's strong, specific issues (with evidence), what's missing, and the top 3 things to fix before sharing. No file is saved by default since the critique is conversational.

## What it checks

- **Clarity** -- Can someone outside the team understand this?
- **Evidence** -- Which claims are backed vs. asserted?
- **Audience fit** -- Does this match your actual personas?
- **Competitive awareness** -- Does this account for competitors?
- **Gaps** -- What will stakeholders ask about?

## Tips

- Run it after `/prd` to catch holes before sharing with eng or stakeholders.
- Works on anything: PRDs, strategy docs, pitches, positioning statements, even your context files.
- It reads your context files to critique against your actual product world, not generic best practices.
- Pair with `/prd` to fix issues: "update the PRD with these fixes."
