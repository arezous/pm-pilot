# /product-teardown

Tear down a competitor's product to understand how it actually works: features, UX flows, architecture, and growth mechanics.

## How to use it

Type `/product-teardown` followed by a product name or URL:

```
/product-teardown Vistaly
/product-teardown https://linear.app
/product-teardown Linear's issue tracking
```

The input is a **product**, not a company. If a company has multiple products, it asks which one to tear down.

You can scope to a specific area ("their AI features", "their onboarding flow") or do a full teardown.

## What you get

A structured teardown saved to `output/competitors/` (e.g., `product-teardown-vistaly-2026-03-28.md`) covering:

- **Context and goal** -- why this teardown, what question to answer
- **Problem, users, JTBD** -- what problem the product solves, for whom
- **User journey** -- onboarding to first value, core usage flow, friction and aha moments
- **Feature analysis** -- each feature tied to a JTBD, with usability, value, and vs-us comparison
- **Growth and business model** -- in-product acquisition hooks, retention mechanics, monetization
- **Technical signals** -- architecture hints, integrations, performance
- **Synthesis** -- strengths, weaknesses, interesting bets, ideas for our product, open questions

## Depth levels

- **Light** -- sections 1-3 only (context, JTBD, user journey). Quick read.
- **Standard** -- all sections, 2-4 features analyzed. Default.
- **Deep** -- all sections, every major feature. Use for top competitors.

## Tips

- Fill in `context/product.md` first so the "vs us" comparisons are grounded.
- Run `/analyze-competitors` first for company-level context. The teardown goes deep on product, not company.
- Existing deep dives are used as starting context automatically.
- Distinguishes observed behavior from inferred architecture. If it can't find something, it says so.
- Say "finalize this" to move the teardown to `context/competitors/` where other skills can reference it.
- Pair with `/prd` to turn "steal" items into feature specs.
