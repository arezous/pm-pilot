# PM Operating System

Your AI-powered copilot for modern product management. Built for Claude Code and Cursor.

## Philosophy

Most PMs use AI the same way they use Google: one-off questions, zero context. This system works differently. You build context about your company, competitors, personas, and product. Every skill draws from that context so outputs are grounded in your actual world, not generic advice.

## Project Structure

```
pmos-starterkit/
├── context/           # What you know (living documents)
│   ├── company.md     # Who you are, goals, constraints
│   ├── competitors.md # Competitive landscape summary
│   ├── personas.md    # Who you serve, their needs
│   ├── product.md     # What you have, what works
│   ├── specs/         # Finalized PRDs, briefs, one-pagers
│   ├── interviews/    # Finalized synthesis and pain points
│   ├── competitors/   # Finalized deep dives and landscapes
│   └── meetings/      # Finalized meeting notes
├── template/          # Output formats and style guides
├── output/            # Drafts and generated artifacts
└── setup/             # Environment configuration
```

Drafts land in `output/`. When finalized, they move to `context/` subfolders (`context/specs/`, `context/interviews/`, `context/competitors/`, `context/meetings/`).

## Skills

| Command | What it does |
|---|---|
| `/prd` | Write a PRD, one-pager, or project brief |
| `/competitors-analyze` | Deep dive on a company or full landscape analysis |
| `/interviews-synthesize` | Turn interview notes into themes and recommendations |
| `/meeting-notes` | Transform meeting transcripts into decisions and action items |
| `/status-update` | Status update matched to the audience |

## Getting Started

1. Clone this repository
2. Set up your environment keys (see [setup/ENV_KEYS_SETUP.md](setup/ENV_KEYS_SETUP.md))
3. Start a conversation and share what you know about your company, product, or market
4. The system will populate your context files and guide you from there
