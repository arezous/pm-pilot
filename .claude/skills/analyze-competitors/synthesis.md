# Synthesis workflow

Produces an actionable evidence base from existing competitive research. No new web research. Cross-cuts what you already know into strategic insights that support decision-making.

## 1. Detect what exists

Inventory all available sources:

**Deep dives and teardowns:** Search `context/competitors/` and `output/competitors/` for `competitive-deep-dive-*.md` and `product-teardown-*.md`. Show what you found:
- "[N] deep dives: [names] (oldest: [date], newest: [date])"
- "[N] teardowns: [names] (oldest: [date], newest: [date])"

**Landscape docs:** Search for `competitive-landscape-*.md` in the same locations. If a recent landscape exists, use it to inform the market structure and positioning.

**If nothing exists:** Stop. "Nothing to synthesize yet. Run `/analyze-competitors [name]` on a few competitors first, or `/analyze-competitors landscape` to map the market."

**Staleness check:** If any doc is older than 3 months, flag it: "[Competitor] deep dive is from [date]. Findings may be stale. Want me to refresh it first, or synthesize with what we have?" Note staleness in the output header if proceeding.

## 2. Read all sources

Read every deep dive, teardown, and landscape doc found. Also read:
- `context/competitors.md` — current competitor summary
- `context/company.md` — company context, market definition, priorities
- `context/product.md` — what you've built, what's broken
- `context/personas.md` — who you serve, their pains

The company, product, and persona context is what turns competitive patterns into strategic insights. Without it, synthesis is just observation.

## 3. Produce the evidence base

Organize findings into these categories. Each one should cross-reference competitive data with your company context and personas. Don't just report what competitors do. Say what it means for you.

### Problem space
What problems exist in this market that competitors aren't solving well? Where are customers underserved? Use evidence from deep dives (weaknesses, complaints), teardowns (UX gaps, missing features), and personas (unmet pains).

### Who's affected
Which customer segments are underserved? Which ICP segments are over-competed (everyone fights for them) vs ignored? Cross-reference with your personas to identify where your users' needs align with competitive gaps.

### Competitive alternatives
Who's there and who's not. Where competitors cluster (table stakes) and where they diverge (strategic seams). What the positioning map reveals about occupied vs empty positions.

For sections that reference teardown data (capabilities, UX patterns): if no teardowns exist, say so and note which competitors would benefit from a `/product-teardown`. Don't infer product details from deep dives alone.

### Our advantage
Why you're positioned to win. Cross-reference your product differentiators (from `context/product.md`) and company strengths (from `context/company.md`) against the gaps and weaknesses found in the competitive analysis. Be specific: "Our X beats their Y because our personas care about Z."

### Timing
Why now matters (or doesn't). Market trends, technology shifts, competitor momentum signals. If a landscape doc exists, pull trends from it. If not, note what timing signals are missing.

### Risks
What could go wrong. Which competitors are moving fast. Which competitive advantages are fragile. What happens if a competitor closes the gap you're counting on.

## 4. Produce opportunities

Top 3 opportunities, each framed as a "we should" statement:

- **[Opportunity]:** We should [action] because [evidence from analysis]. This targets [segment] where [competitive gap]. Product/pricing/GTM angle: [specific approach].

Ground every opportunity in evidence from the analysis. No speculation. If the evidence is thin, say so.

## 5. Assess coverage

After the synthesis, assess the quality of your competitive intelligence:

- **What we know well:** Competitors with deep dives or strong internal intel. High confidence findings.
- **What's shallow:** Competitors with web-only profiles. Findings that rely on marketing pages, not verified data.
- **What's missing:** Competitor types underrepresented (no indirect competitors researched? no substitutes?). Segments not covered. Questions that can't be answered with current data.
- **Recommended next steps:**
  - [ ] Deep dive on [competitor] — [reason]
  - [ ] Teardown on [competitor] — [reason]
  - [ ] Refresh [competitor] deep dive — [reason: older than 3 months]

## 6. Save and update context

**Save** to `output/competitors/competitive-synthesis-[YYYY-MM-DD].md` with `**Status:** Draft`.

**Update `context/competitors.md`:** Offer to update the **Strategic Insights** section at the bottom. This section should follow the structure:

```markdown
## Strategic Insights

_Last synthesized: [date]. Source: output/competitors/competitive-synthesis-[date].md_

### Patterns
- [Key convergence/divergence patterns]

### Top Threats
- [With reasoning]

### Top Opportunities
- [We should statements with evidence]

### Coverage
- Know well: [list]
- Shallow: [list]
- Missing: [list]
- Next steps: [list]
```

Do NOT rewrite individual competitor entries. Those are maintained by deep dive, landscape, and monitoring. Synthesis only owns the Strategic Insights section.
