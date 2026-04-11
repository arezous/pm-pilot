# Landscape workflow

Builds a structured competitive landscape: the universe of competitors, profiles for each, and a positioning map. Uses a fixed sequence so output is consistent across markets.

## Before you start

1. **Read context.** Read `context/company.md` for ICP and market definition. Read `context/product.md` for current product state. Read `context/personas.md` for who you serve.

2. **Check existing work.** Search `context/competitors/` and `output/competitors/` for:
   - Existing deep dives (`competitive-deep-dive-*.md`)
   - Existing teardowns (`product-teardown-*.md`)
   - Previous landscape docs (`competitive-landscape-*.md`)

   If 3+ deep dives/teardowns exist, tell the user: "Found [N] existing deep dives/teardowns. Want me to build the landscape from what we have, do fresh research, or both?" If they choose synthesis only (no new research), switch to the [synthesis workflow](synthesis.md).

3. **Pre-populate from existing deep dives.** For each deep dive or teardown found, extract: competitor name, type, ICP, segment, pricing, positioning, strengths, weaknesses. Add these to the universe table with `Source: [deep dive, YYYY-MM-DD]` and `Confidence: High`. These are verified starting points, not assumptions.

## Step 1: Build the universe

Identify competitors across all four types:

**Direct** (same product, same buyers, target 3-5):
- Search G2/Capterra category listings for the market category
- Check prospect shortlists and win/loss data in `data/meetings/`, `context/meetings/`
- Search for "[category] alternatives" and "[category] competitors"

**Indirect** (same problem, different approach, target 2-3):
- Apply JTBD lens: what else do customers use to solve this problem?
- Check customer interviews for "if our product disappeared, what would you use?"
- Look for lost deals where the customer chose a different approach, not just a different vendor

**Substitutes** (could eliminate the category, target 1-2):
- Manual processes, spreadsheets, internal tools that customers use instead
- Emerging technology that could make the category obsolete
- Non-consumption: customers who choose to do nothing

**Potential entrants** (not competing yet, positioned to enter, target 1-2):
- Adjacent market players with distribution and resources
- Companies with M&A activity in or near the space
- Job postings in your domain from companies outside it

For competitors NOT found in existing deep dives, use web search to gather basic metadata. Tag these as `Source: [web research]` and `Confidence: Medium` or `Low`.

Build the universe table from the template with all competitors listed.

## Step 2: Create competitor profiles

For each tracked competitor, fill the profile card from the template:

**If a deep dive exists:** Reuse data from the deep dive. Don't re-research what's already verified. Fill the profile card fields from deep dive sections. Tag as `Source: [deep dive, YYYY-MM-DD]`.

**If no deep dive exists:** Research using web search. Fill the same profile card fields. Tag as `Source: [web research]`. Keep profiles lightweight. This is enough to compare, not enough to act on individually. If deeper analysis is needed, recommend a deep dive in the coverage assessment.

For every competitor, include the strategic assessment section:
- Where they beat us (2-3 bullets, grounded in evidence)
- Where we beat them (2-3 bullets, framed through personas)
- Likely next moves (1-3 bullets, based on hiring, funding, recent launches)

## Step 3: Create positioning map

Build one 2x2 perceptual map.

**Choose axes based on what differentiates this specific competitive set.** Don't default to price vs features. Axes should be:
- Important to customers (influences the buying decision)
- Observable (you can measure or see it in the market)
- Actionable (you can change your position)

Good axis examples: solution breadth (point solution → platform), target segment (SMB → enterprise), AI depth (manual → AI-native), sales motion (self-serve → sales-led), workflow scope (single task → full lifecycle).

Plot each competitor. Then write:
- **Clusters:** where competitors bunch together
- **White spaces:** positions no one occupies
- **Where we sit:** our current position and why

## Step 4: Synthesize

Write the synthesis section from the template:
- Clusters and gaps (table stakes vs opportunities, over-served vs under-served)
- Top 3 threats with reasoning
- Top 3 opportunities with product, pricing, or GTM angle

Then write the coverage assessment:
- What we know well (deep dive backed)
- What's shallow (web-only)
- What's missing (types, segments)
- Recommended next steps (which deep dives or teardowns to run)

## Save

Save to `output/competitors/competitive-landscape-[market]-[YYYY-MM-DD].md`.
Include `**Status:** Draft` in the body.
Offer to update `context/competitors.md` with new or updated entries.
