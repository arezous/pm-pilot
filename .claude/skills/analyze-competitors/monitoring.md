# Monitoring workflow

Use when a baseline analysis already exists and you need to catch what changed. Run monthly or before key planning sessions.

1. **Find the baseline.** Check `context/competitors/` and `output/competitors/` for the most recent deep dive or monitoring report. If none exists, don't block. Instead, offer: "No baseline analysis exists yet. I can either run a quick baseline from what you know plus web research, or do a full deep dive first. Which do you prefer?" If the PM chooses the quick baseline, gather competitor names and key details from the PM, supplement with web research, and use that as the starting point for monitoring.

2. **Check internal intel since last report.** Search for new competitor mentions added after the last report date. Look for new sales losses, customer quotes, or feature requests citing competitors.
  - `data/interviews/` and `data/meetings/` -- raw transcripts
  - `context/interviews/` and `context/meetings/` -- finalized notes
  - `output/interviews/` and `output/meetings/` -- draft synthesis and notes

   If none of these directories exist or no new mentions are found, say "No new internal intel since last report" and move to step 3.

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

## Monitoring output format

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
