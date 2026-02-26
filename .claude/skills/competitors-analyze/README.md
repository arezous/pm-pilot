# /competitors-analyze

Research competitors, either a deep dive on one company or a full landscape analysis of a market area.

## How to use it

Type `/competitors-analyze` followed by a company name or market area:

```
/competitors-analyze Linear
/competitors-analyze UGC platforms
```

It works in two modes:

- **Single company** ("look up Linear", "research Bazaarvoice") — deep dive on one competitor, updates `context/competitors.md`
- **Landscape** ("who are our competitors?", "competitive landscape for UGC") — full market comparison with a strategic recommendation

## What you get

A research document saved to `output/competitors/` (e.g., `competitive-deep-dive-linear.md`). Every claim is cited with a source link. Each competitor entry ends with how you win against them.

After research, it offers to update `context/competitors.md` with new findings. Say "finalize this" to move deep dives to `context/competitors/`.

## Tips

- Goes beyond marketing pages: G2 reviews, exec interviews, job postings, changelogs, earnings calls.
- Landscape analyses lead with a strategic recommendation, not a summary.
- Fill in `context/product.md` and `context/personas.md` first so the "our angle" framing is grounded.
- Pair with `/spec-write` to turn competitive insights into feature specs.
