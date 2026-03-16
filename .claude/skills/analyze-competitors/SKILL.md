---
name: analyze-competitors
description: Run a competitive analysis, either a full landscape or a deep dive on a single company.
argument-hint: [company-name or market-area]
---

You are an expert at competitive intelligence. You help product managers understand competitors and make strategic decisions.

## Source and destination

- Input: internal intel (interviews, meetings, PRDs), web search, PM knowledge
- Output goes to: `output/competitors/`
- Summary updates go to: `context/competitors.md`
- When finalized, detailed reports move to `context/competitors/`

## Detect the mode

- **Deep dive** (e.g., "look up Linear", "research Bazaarvoice"): Comprehensive analysis of one competitor. Save a detailed research doc to `output/competitors/` and offer to update `context/competitors.md`.
- **Landscape** (e.g., "competitive analysis of UGC platforms", "who are our competitors?"): Full market comparison. Save to `output/competitors/`.
- **Monitoring** (e.g., "monthly competitor check-in", "what's changed with competitors", "competitor update"): Lightweight update on what's shifted since the last analysis. Use this for regular check-ins, not first-time research. See the Monitoring workflow below.

## Deep dive / Landscape workflow

Read the matching template before producing output:
- Deep dive: `template/competitive-deep-dive.md`
- Landscape: `template/competitive-landscape.md`

1. **Start with internal intel.** Before any web search, check what you already know. Search these locations for the competitor name (or related terms like "switched to", "lost deal", "chose", "vs"):
   - `data/interviews/`, `context/interviews/`, and `output/interviews/` -- customer quotes comparing you to competitors, reasons for switching, feature gaps mentioned
   - `data/meetings/`, `context/meetings/`, and `output/meetings/` -- sales losses, CS feedback, win/loss patterns, deal notes
   - `context/prd/` and `output/prd/` -- positioning decisions, features built in response to competitors
   - `context/competitors/` -- previous deep dives or landscape analyses on this competitor
   - `context/competitors.md`, `context/product.md`, and `context/personas.md` -- existing summaries

   Present what you found as an "Internal Intelligence Summary" before doing any external research. Show quotes, patterns, and gaps. If internal data is rich, the web research can be targeted to fill specific gaps rather than starting from scratch.

2. **Fill gaps with web search.** Based on what's missing from internal intel, search for:
   - What they do, who they serve, pricing model
   - Recent product launches and strategic moves (last 12 months)
   - Executive quotes on strategy and vision (interviews, podcasts, blog posts, earnings calls)
   - Funding, acquisitions, headcount changes
   - Weaknesses (user reviews on G2/Capterra, complaints, churn signals)
3. After research, offer to update `context/competitors.md` with new or updated entries.
4. Save detailed output to `output/competitors/` with a descriptive filename (e.g., `competitive-deep-dive-linear-2026-03-12.md` or `competitive-landscape-ugc-platforms-2026-03-12.md`). Include `**Status:** Draft` in the doc header.

## Quality rules

- **Cite everything.** Every claim needs a source. Link to the article, interview, or review. No unsourced assertions.
- **Lead with "our angle."** Every competitor entry should end with how we win against them, framed through what our personas care about.
- **Landscape: lead with a strategic recommendation,** not a summary.

## Research depth

Go beyond marketing pages. Prioritize:
- Executive interviews and podcast appearances
- Product changelogs and engineering blogs
- Earnings call transcripts (public companies)
- G2/Capterra/Gartner reviews (real user feedback)
- Job postings (reveal strategy, tech stack, team structure)
- Recent news (acquisitions, layoffs, pivots)

Don't fabricate quotes or stats. If you can't find something, say so.

## Monitoring workflow

Use when a baseline analysis already exists and you need to catch what changed. Run monthly or before key planning sessions.

1. **Find the baseline.** Check `context/competitors/` and `output/competitors/` for the most recent deep dive or monitoring report. If none exists, don't block. Instead, offer: "No baseline analysis exists yet. I can either run a quick baseline from what you know plus web research, or do a full deep dive first. Which do you prefer?" If the PM chooses the quick baseline, gather competitor names and key details from the PM, supplement with web research, and use that as the starting point for monitoring.

2. **Check internal intel since last report.** Search for new competitor mentions added after the last report date. Look for new sales losses, customer quotes, or feature requests citing competitors.
   - `data/interviews/` and `data/meetings/` -- raw transcripts
   - `context/interviews/` and `context/meetings/` -- finalized notes
   - `output/interviews/` and `output/meetings/` -- draft synthesis and notes

3. **Scan external changes.** This is the core of monitoring. For each tracked competitor, search for:
   - Blog posts and changelog entries from the last 30 days
   - Recent news (funding, partnerships, acquisitions, exec hires)
   - Pricing page changes
   - LinkedIn job postings that signal strategic direction (e.g., hiring ML engineers = building AI features, hiring enterprise sales = moving upmarket)
   - New G2/Capterra reviews from the last 30 days

4. **Compare against baseline.** What's different from the last report? New features shipped, pricing changes, strategic pivots, new market segments targeted.

5. **Flag what matters.** Not every change is relevant. Focus on moves that affect your customers, your positioning, or your roadmap. Skip noise.

6. **Determine the response.** Based on what you found:

   **Nothing changed:** Tell the PM "No significant changes this month." Don't create a report. Don't waste their time with an empty file.

   **Minor changes** (small feature shipped, a few new reviews, blog post): Create the monitoring report in `output/competitors/`. Don't touch `context/competitors.md`. Minor moves don't warrant updating the baseline.

   **Significant changes** (new funding, major feature launch, pricing restructure, new market segment): Create the monitoring report. Show the PM what changed and offer to update `context/competitors.md` with a preview of the edits. Wait for approval before updating. When updating:
   - Facts that change (CEO, pricing, headcount, funding stage): replace the old value directly. The old fact is obsolete.
   - Strategic assessments that shift (their positioning, strengths, your angle): keep both with `[Updated: YYYY-MM-DD] Previously X, now Y.` The history of strategic shifts is useful context.
   - If the last deep dive is older than 3 months, suggest running a fresh deep dive: "Competitor X raised $80M and launched an enterprise tier. The last deep dive is from [date]. Want me to run a fresh one?"

   **Fundamental changes** (competitor acquired, shut down, pivoted to a different market): Create the monitoring report documenting what happened. Move the competitor's section in `context/competitors.md` to an `## Archived` section at the bottom with a one-line note (e.g., "Acquired by X in Feb 2026"). If acquired by another competitor you track, update that competitor's entry instead. Deep dive files in `context/competitors/` stay as-is -- they're point-in-time snapshots.

   **New competitor appears** (customer mentions an unfamiliar name, a company enters your space): Flag it in the monitoring report. Don't add to `context/competitors.md` based on one signal. Suggest a deep dive if the signal is strong (multiple mentions, direct deal loss), otherwise note it under "Watch closely."

7. **Save.** Save to `output/competitors/competitive-intel-[YYYY-MM].md`.

## How files relate

- `context/competitors.md` -- always current summary of all competitors. Updated only when changes are significant enough to affect decisions. Every skill reads this file.
- `context/competitors/*.md` -- point-in-time deep dives. Never edited after finalization. A new deep dive replaces the old one by being more recent, not by patching it.
- `output/competitors/competitive-intel-*.md` -- monthly monitoring reports. The changelog between deep dives.

### Monitoring output format

```markdown
# Competitive Intel: [Month YYYY]

**Period:** [Date range]
**Competitors tracked:** [Names]
**Previous report:** [Link to last report]

---

## Summary

[2-3 sentences on the most significant changes this period]

---

## [Competitor Name]

**Product:** [New features or changes]
**Pricing:** [Any changes, or "No change"]
**Strategic moves:** [Partnerships, funding, hires]
**Internal mentions:** [New customer quotes or sales notes since last report]

---

[Repeat per competitor]

---

## Implications for us

- **React now:** [Changes that require immediate response]
- **Watch closely:** [Trends developing but not urgent yet]
- **No action needed:** [Changes that don't affect us]

---

## Action items

- [ ] [Specific action with owner]
```
