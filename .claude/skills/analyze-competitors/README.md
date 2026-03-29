# /analyze-competitors

Research competitors, synthesize existing analysis, or track what's changed.

## How to use it

Type `/analyze-competitors` followed by a company name, market area, or action:

```
/analyze-competitors Linear
/analyze-competitors UGC platforms
/analyze-competitors synthesize competitors
/analyze-competitors monthly check-in
```

It works in four modes:

- **Deep dive** ("look up Linear", "research Bazaarvoice") — comprehensive analysis of one competitor, updates `context/competitors.md`. If a previous deep dive exists, asks whether to refresh or start new.
- **Landscape** ("who are our competitors?", "competitive landscape for UGC") — full market comparison with a strategic recommendation. If 3+ deep dives already exist, offers to synthesize instead.
- **Synthesis** ("synthesize competitors", "pull it all together") — cross-cutting analysis of existing deep dives and teardowns. No new web research. Flags stale docs before proceeding.
- **Monitoring** ("monthly check-in", "what's changed with competitors") — lightweight update on what shifted since the last analysis, combining new internal mentions with external changes.

## What you get

**Deep dive / Landscape:** A research document saved to `output/competitors/`. Every claim is cited with a source link. Each competitor entry ends with how you win against them.

**Synthesis:** A strategic landscape doc built from your existing deep dives and teardowns. Focuses on cross-cutting patterns (convergence, divergence, gaps, threat ranking) rather than per-competitor summaries.

**Monitoring:** A short update saved to `output/competitors/competitive-intel-[YYYY-MM].md` covering product changes, pricing shifts, strategic moves, and new internal mentions since the last report. Ends with what to react to, what to watch, and what to ignore.

After research, it offers to update `context/competitors.md` with new findings. Say "finalize this" to move reports to `context/competitors/`.

## Audience

Default output is for the PM (detailed, decision-oriented). Specify the audience to adjust tone:

- "this is for my VP" — strategic positioning, market risk, less feature detail
- "for the sales team" — win/loss angles, objection handling, pricing comparison
- "for the eng team" — architecture, tech stack, build-vs-buy

## Tips

- Checks interviews, meetings, specs, and past analyses for internal intel before web search. Skips straight to web research if no internal data exists yet.
- Goes beyond marketing pages: G2 reviews, exec interviews, job postings, changelogs, earnings calls.
- Fill in `context/product.md` and `context/personas.md` first so the "our angle" framing is grounded.
- Pair with `/product-teardown` to go deeper on a competitor's product (features, UX, architecture).
- Pair with `/prd` to turn competitive insights into feature specs.
