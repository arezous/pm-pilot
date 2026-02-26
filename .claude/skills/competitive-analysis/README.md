# /competitive-analysis

Research competitors, either a deep dive on one company or a full landscape analysis of a market area.

## How to use it

Type `/competitive-analysis` followed by a company name or market area:

```
/competitive-analysis Linear
/competitive-analysis UGC platforms
```

It works in two modes:

- **Single company** ("look up Linear", "research Bazaarvoice") — deep dive on one competitor, updates `context/competitors.md`
- **Landscape** ("competitive analysis of UGC platforms", "who are our competitors?") — full market comparison using the competitive analysis template

## What you get

A research document saved to `output/` (e.g., `competitive-deep-dive-linear.md` or `competitive-analysis-ugc-platforms.md`). Every claim is cited with a source link. Each competitor entry ends with how you win against them.

After research, it will offer to update `context/competitors.md` with new findings.

## Tips

- It goes beyond marketing pages: G2 reviews, exec interviews, job postings, changelogs, earnings calls.
- Landscape analyses lead with a strategic recommendation, not a summary.
- Fill in `context/product.md` and `context/personas.md` first so the "our angle" framing is grounded.
