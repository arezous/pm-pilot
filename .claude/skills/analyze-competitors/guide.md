# Guide workflow

Triggered when `/analyze-competitors` is invoked with no arguments. Reads context state, assesses where the user is in the CI journey, and recommends the specific next step.

## 1. Read context state

Check these sources silently:

- `context/company.md` — does a Market section exist? (JTBD, ICP, scope)
- `context/competitors.md` — how many competitor entries? Is there a Strategic Insights section? How recent?
- `context/competitors/` and `output/competitors/` — count:
  - Deep dives (`competitive-deep-dive-*.md`) with dates
  - Teardowns (`product-teardown-*.md`) with dates
  - Landscape docs (`competitive-landscape-*.md`) with dates
  - Synthesis docs (`competitive-synthesis-*.md`) with dates
  - Monitoring reports (`competitive-intel-*.md`) with dates

## 2. Recommend next step

Based on what exists, give one clear recommendation. Not a menu. Tell the user what to do and why.

**No market definition (company.md missing or no Market section):**

"I don't know what market you're in yet. Tell me what problem your product solves and for who, and I'll map out the competitive space from there."

If company.md is entirely empty, suggest `/onboard` instead: "Your workspace is empty. Run `/onboard` and share what you know about your product. I'll sort it and then we can look at the competition."

**Market defined, no landscape:**

"You're in [market]. I haven't mapped the competitive space yet. I'll build a universe of competitors, profile each one, and show you where the gaps are. Ready?"

**Landscape exists, few or no deep dives:**

Show a brief status, then recommend:

"You have a landscape from [date] with [N] competitors. But I only have surface-level info on most of them. I'd go deeper on [name] and [name] first — [reason: closest to your ICP / highest threat / biggest unknown]. Just say the name."

**Deep dives exist, no synthesis:**

"You have [N] deep dives and [N] teardowns. That's enough to cross-cut. I can tell you where the opportunities are, where you're strong, and what to watch out for. Want me to synthesize?"

**Synthesis exists but older than 1 month:**

"Your last synthesis is from [date] ([N weeks] ago). You have [N] deep dives. Want me to check what's changed since then, or refresh the synthesis?"

**Everything is current (synthesis < 1 month, monitoring recent):**

"Your competitive intelligence is current. Last synthesis: [date]. [N] competitors tracked."

Then summarize the key finding from the Strategic Insights section of `context/competitors.md` (1-2 sentences). Follow with:

"Want to go deeper on a specific competitor, or is there a new player you've heard about?"

## 3. Status snapshot (conditional)

Only show the full status snapshot when context is partially filled (some things exist, some don't). Don't show it when context is empty (just say what to do first) or when everything is current (just summarize).

```
CI status:
- Market: [defined / missing]
- Landscape: [date] / not yet
- Deep dives: [N] — [names]
- Teardowns: [N] — [names]
- Synthesis: [date] / not yet
- Last monitoring: [date] / never
```
