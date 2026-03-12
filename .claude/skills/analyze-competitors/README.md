# /analyze-competitors

Research competitors, either a deep dive on one company, a full landscape analysis, or a monthly monitoring check-in.

## How to use it

Type `/analyze-competitors` followed by a company name, market area, or check-in request:

```
/analyze-competitors Linear
/analyze-competitors UGC platforms
/analyze-competitors monthly check-in
```

It works in three modes:

- **Deep dive** ("look up Linear", "research Bazaarvoice") — comprehensive analysis of one competitor, updates `context/competitors.md`
- **Landscape** ("who are our competitors?", "competitive landscape for UGC") — full market comparison with a strategic recommendation
- **Monitoring** ("monthly check-in", "what's changed with competitors") — lightweight update on what shifted since the last analysis, combining new internal mentions with external changes

## What you get

**Deep dive / Landscape:** A research document saved to `output/competitors/` (e.g., `competitive-deep-dive-linear.md`). Every claim is cited with a source link. Each competitor entry ends with how you win against them.

**Monitoring:** A short update saved to `output/competitors/competitive-intel-[YYYY-MM].md` covering product changes, pricing shifts, strategic moves, and new internal mentions since the last report. Ends with what to react to, what to watch, and what to ignore.

After research, it offers to update `context/competitors.md` with new findings. Say "finalize this" to move reports to `context/competitors/`.

## Tips

- Checks your interviews, meetings, specs, and past analyses for internal intel before any web search.
- Goes beyond marketing pages: G2 reviews, exec interviews, job postings, changelogs, earnings calls.
- Landscape analyses lead with a strategic recommendation, not a summary.
- Run monitoring monthly or before key planning sessions to stay current.
- Fill in `context/product.md` and `context/personas.md` first so the "our angle" framing is grounded.
- Pair with `/prd` to turn competitive insights into feature specs.
