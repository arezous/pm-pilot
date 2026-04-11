# Deep dive workflow

Comprehensive analysis of one competitor. Produces a structured deep dive that feeds directly into the landscape universe (via the Profile Summary) and the synthesis evidence base.

## 0. Check for existing work

Check `context/competitors/` and `output/competitors/` for an existing deep dive on the same competitor (e.g., `competitive-deep-dive-linear-*.md`). If one exists, tell the user: "A deep dive from [date] already exists. Want me to refresh it with new research, or start a new one from scratch?" Wait for their answer before proceeding.

Also check `context/competitors.md` for the competitor's entry. Note what type (D/I/S/P) they are classified as, if known.

## 1. Start with internal intel

Before any web search, check what you already know. Search these locations for the competitor name (or related terms like "switched to", "lost deal", "chose", "vs"):
- `data/interviews/`, `context/interviews/`, and `output/interviews/` -- customer quotes comparing you to competitors, reasons for switching, feature gaps mentioned
- `data/meetings/`, `context/meetings/`, and `output/meetings/` -- sales losses, CS feedback, win/loss patterns, deal notes
- `context/prd/` and `output/prd/` -- positioning decisions, features built in response to competitors
- `context/competitors/` -- previous deep dives or landscape analyses on this competitor
- `context/competitors.md`, `context/product.md`, and `context/personas.md` -- existing summaries

Present what you found as an "Internal Intelligence Summary" before doing any external research. Show quotes, patterns, and gaps. If internal data is rich, the web research can be targeted to fill specific gaps rather than starting from scratch. If none of these directories exist or no relevant mentions are found, say "No internal intel found for [competitor], proceeding directly to web research." Do not fabricate or infer internal intelligence that doesn't exist.

## 2. Fill gaps with web search

Based on what's missing from internal intel, search for:
- What they do, who they serve, pricing model
- Recent product launches and strategic moves (last 12 months)
- Executive quotes on strategy and vision (interviews, podcasts, blog posts, earnings calls)
- Funding, acquisitions, headcount changes
- Weaknesses (user reviews on G2/Capterra, complaints, churn signals)
- Job postings that signal strategic direction

## 3. Tag sources and confidence

Every claim in the deep dive needs a source and confidence level:

- **[Source: internal intel, High]** — from interviews, meetings, or deal notes
- **[Source: deep dive refresh, High]** — verified against previous deep dive
- **[Source: web, product docs, High]** — from official docs, pricing pages, changelogs
- **[Source: web, reviews, Medium]** — from G2/Capterra reviews (real but individual)
- **[Source: web, news/blog, Medium]** — from articles, press, blog posts
- **[Source: web, inferred, Low]** — inferred from job postings, indirect signals
- **[Assumption, verify]** — no source, your best guess

Don't tag every line. Tag key claims: ICP, pricing, strategy, strengths, weaknesses, likely next moves.

## 4. Write the deep dive

Follow the template (`template/competitive-deep-dive.md`).

**Start with the Profile Summary.** This is the structured extract that the landscape uses for pre-population. Fill every field. This section should be self-contained: someone reading just the profile summary gets the essential picture.

Then fill the full sections (1-6) with the depth that makes a deep dive valuable. The profile summary is the headline. The sections are the evidence.

**Classify the competitor type** in the frontmatter: D (direct), I (indirect), S (substitute), P (potential). If the landscape already classified them, use the same type. If not, determine it based on: do they sell the same product to the same buyers (D)? Solve the same problem differently (I)? Could eliminate the category (S)? Not competing yet but could enter (P)?

## 5. Save

Save to `output/competitors/competitive-deep-dive-[name]-[YYYY-MM-DD].md`.
- Populate all frontmatter fields: `name`, `type_classification`, `segment`, `icp`, `overlap_area`, `threat_level`, `last_reviewed`, `source_quality`.
- Include `**Status:** Draft` in the body after the frontmatter.

## 6. Connect

After saving:
- Offer to update `context/competitors.md` with new or updated entries. Use the Profile Summary fields to write a structured entry.
- If a landscape exists, note whether the universe table needs updating with this competitor's data.
- If the user asks to go deeper on the product's features, UX, or technical architecture, suggest running `/product-teardown [name]` instead of expanding the deep dive.
