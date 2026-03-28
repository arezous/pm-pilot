# /break-down

Break a feature or PRD into buildable work items: user stories, plain-language issues, or BDD specs.

## How to use it

Type `/break-down` followed by the feature name or PRD reference:

```
/break-down search redesign
/break-down output/prd/prd-onboarding-v2.md
/break-down [paste requirements]
```

Accepts: PRD references, feature descriptions, pasted requirements, or file paths.

## What you get

A set of work items saved to `output/prd/` alongside the parent PRD (e.g., `stories-search-redesign-2026-03-28.md`). Each item includes:

- **User story** or plain-language description
- **Acceptance criteria** (testable)
- **Dependencies** and sequencing
- **Size estimate** (asks for PM input, doesn't guess)

Output is flagged as a first draft for refinement with engineering and design, not a final spec.

## Tips

- Run after `/prd` to turn a spec into buildable work.
- It reads `context/product.md` and `context/personas.md` to ground stories in real user needs.
- Checks for existing PRDs in `output/prd/` and `context/prd/` when you reference a feature by name.
- Stories are conversation starters, not hand-offs. Review with eng before committing.
- Pair with `/prioritize` to decide which stories to build first.
