# Deep dive workflow

0. **Check for existing work.** Check `context/competitors/` and `output/competitors/` for an existing deep dive on the same competitor (e.g., `competitive-deep-dive-linear-*.md`). If one exists, tell the PM: "A deep dive from [date] already exists. Want me to refresh it with new research, or start a new one from scratch?" Wait for their answer before proceeding.

1. **Start with internal intel.** Before any web search, check what you already know. Search these locations for the competitor name (or related terms like "switched to", "lost deal", "chose", "vs"):
  - `data/interviews/`, `context/interviews/`, and `output/interviews/` -- customer quotes comparing you to competitors, reasons for switching, feature gaps mentioned
  - `data/meetings/`, `context/meetings/`, and `output/meetings/` -- sales losses, CS feedback, win/loss patterns, deal notes
  - `context/prd/` and `output/prd/` -- positioning decisions, features built in response to competitors
  - `context/competitors/` -- previous deep dives or landscape analyses on this competitor
  - `context/competitors.md`, `context/product.md`, and `context/personas.md` -- existing summaries

   Present what you found as an "Internal Intelligence Summary" before doing any external research. Show quotes, patterns, and gaps. If internal data is rich, the web research can be targeted to fill specific gaps rather than starting from scratch. If none of these directories exist or no relevant mentions are found, say "No internal intel found for [competitor/area], proceeding directly to web research." Do not fabricate or infer internal intelligence that doesn't exist.

2. **Fill gaps with web search.** Based on what's missing from internal intel, search for:
  - What they do, who they serve, pricing model
  - Recent product launches and strategic moves (last 12 months)
  - Executive quotes on strategy and vision (interviews, podcasts, blog posts, earnings calls)
  - Funding, acquisitions, headcount changes
  - Weaknesses (user reviews on G2/Capterra, complaints, churn signals)
3. After research, offer to update `context/competitors.md` with new or updated entries.
4. **Save** to `output/competitors/competitive-deep-dive-[name]-[YYYY-MM-DD].md`.
  - Populate frontmatter fields: `name`, `segment`, `icp`, `overlap_area`, `threat_level`, `last_reviewed`.
  - Include `**Status:** Draft` in the body after the frontmatter.
5. If the PM asks to go deeper on the product's features, UX, or technical architecture, suggest running `/product-teardown [name]` instead of expanding the deep dive.
