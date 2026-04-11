# Synthesis workflow

Use when explicitly triggered by the PM or when they choose synthesis over fresh landscape research. Produces cross-cutting strategic analysis from existing documents, no new web research.

1. **Inventory existing work.** List all deep dives and teardowns in `context/competitors/` and `output/competitors/`. Show the PM what you found with dates:
  - "[N] deep dives: [names] (oldest: [date], newest: [date])"
  - "[N] teardowns: [names] (oldest: [date], newest: [date])"
  - If no deep dives or teardowns exist, stop: "Nothing to synthesize yet. Run `/analyze-competitors [name]` on a few competitors first, then come back."
  - If any doc is older than 3 months, flag it: "[Competitor] deep dive is from [date]. Findings may be stale. Want me to refresh it first, or synthesize with what we have?" If they proceed anyway, note the staleness in the output header and flag which sections rely on outdated sources.

2. **Read all source docs.** Read every deep dive and teardown found. Also read `context/competitors.md`, `context/product.md`, and `context/personas.md` for framing.

3. **Produce the synthesis** following the landscape template. Go beyond summarizing individual competitors. The value of synthesis is in cross-cutting patterns:
  - **Where competitors converge**: table-stakes features, shared pricing models, common GTM motions. These are the baseline, not differentiators.
  - **Where competitors diverge**: positioning splits, architectural bets, audience choices. These are the strategic seams where you can win.
  - **Gaps no one fills**: needs from your personas that no competitor addresses well. Use data from deep dives and teardowns, not speculation.
  - **Positioning map**: place competitors on axes that reveal strategic insight. Choose axes based on what actually differentiates the set (don't default to price vs features).
  - **Threat ranking**: which competitors matter most right now, based on overlap with your ICP, momentum signals, and capability gaps.
  - **Implications**: where to lean in, where not to compete, open questions to validate. Be specific ("build X before competitor Y adds it" not "invest in differentiation").

   For sections that reference teardown data (capability landscape, UX patterns): if no teardowns exist, say so and note which competitors would benefit from a `/product-teardown`. Don't infer product details from deep dives alone.

4. **Save** to `output/competitors/competitive-landscape-[YYYY-MM-DD].md`. Offer to update `context/competitors.md`.
