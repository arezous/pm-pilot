# PM Pilot v2.0.0

Your AI-powered copilot for modern product management. Built for Claude Code, Cursor, and Codex.

For product managers, product leads, and anyone making product decisions.

## Why This, Not a Blank AI Chat

Most PMs use AI the same way they use Google: one-off questions, zero memory. Next conversation, you start from scratch. This system works differently:

- **Context compounds.** You build knowledge about your company, competitors, personas, and product. Every skill draws from that context so outputs are grounded in your actual world, not generic advice.
- **Skills, not prompts.** Instead of crafting the right prompt every time, you run `/prd` or `/analyze-competitors` and get structured output that follows proven PM frameworks.
- **The system learns your product.** The more you use it, the sharper it gets. Interview insights refine personas. Competitive research informs prioritization. PRDs reference real user pain.

```
/onboard → /analyze-competitors → /synthesize-interviews
                ↓                         ↓
          context grows ──────→ /prioritize → /prd → /break-down
                                    ↑
              /triage-feedback ──────┘
```

## Quick Start

**Requires [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Cursor](https://www.cursor.com/), or Codex.**

```bash
# 1. Clone
git clone <repo-url>
cd pm-pilot

# 2. Open in Claude Code, Cursor, or Codex

# 3. Set up your context
/onboard
```

`/onboard` walks you through populating your company, competitor, persona, and product context. You don't need to fill everything in before you start. Skills work with whatever context exists and ask you directly when something is missing.

## Project Structure

```
.claude/
  skills/          # Skill definitions (SKILL.md + README.md each)
context/           # What you know (living documents, grows through use)
  company.md       # Who you are, goals, constraints
  competitors.md   # Competitive landscape summary
  personas.md      # Who you serve, their needs
  product.md       # What you have, what works
data/              # Raw source material (transcripts, exports, dumps)
template/          # Output formats and style guides
  styles/          # Audience-specific styles (executive, Slack, Notion)
output/            # Drafts and generated artifacts
```

Drafts land in `output/`. When finalized, they move to `context/` subfolders (e.g., `context/prd/`, `context/competitors/`). Folders are created as the work requires them.

## Skills

| Command | What it does |
|---|---|
| `/onboard` | Set up your context files (company, competitors, personas, product) |
| `/prd` | Write a PRD, one-pager, or project brief |
| `/analyze-competitors` | Deep dive on a company or full landscape analysis |
| `/product-teardown` | Tear down a competitor's product: features, UX, architecture |
| `/synthesize-interviews` | Turn interview notes into themes and recommendations |
| `/meeting-notes` | Transform meeting transcripts into decisions and action items |
| `/status-update` | Status update matched to the audience |
| `/prioritize` | Decide what to build by scoring features against context |
| `/triage-feedback` | Categorize, prioritize, and route customer feedback |
| `/break-down` | Break a feature or PRD into buildable work items |
| `/release-notes` | Draft release notes or changelog from shipped work |
| `/critique` | Pressure-test a document against your product context |

Every skill accepts input three ways: paste content directly, drop a file path into the terminal, or reference a workspace file. No setup required to start using them.

## The Context System

Your context lives in `context/` (gitignored, stays local). Four files, built through `/onboard`:

| File | What | How it grows |
|---|---|---|
| `company.md` | Who you are, priorities, constraints | You fill it, refine over time |
| `competitors.md` | Competitive landscape summary | `/analyze-competitors` updates it |
| `personas.md` | Users, goals, pains with signal strength | `/synthesize-interviews` enriches it |
| `product.md` | What you have, differentiators, current state | Updated as you ship and learn |

Skills read from these files. Your product data never leaves your machine.

## Using PM Pilot in Codex

In Codex, type the same PM Pilot command names at the start of your message:

- `/onboard`, `/prd`, `/analyze-competitors`, `/product-teardown`
- `/synthesize-interviews`, `/meeting-notes`, `/status-update`
- `/prioritize`, `/triage-feedback`, `/break-down`, `/release-notes`, `/critique`

This is command-name parity in chat. It does not imply native slash-command registration.

## Flexible Input

You can feed information to any skill three ways:

- **Paste it** directly in the conversation (transcript, requirements, feedback, etc.)
- **Drop a file path** into the terminal (drag a file in, the skill reads it automatically)
- **Reference a workspace file** by name (e.g., "use the search PRD", "synthesize last week's interviews")

External files (like `~/Downloads/interview-notes.md`) are processed immediately. The skill will offer to save them to the workspace for future use.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Cursor](https://www.cursor.com/), or Codex
- No dependencies, no installs, no API keys

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add skills, templates, and improvements.

## Feedback

This is an early release. Your feedback makes it better.

- **Report bugs or suggest features:** [Open an issue](../../issues)
- **Share how you're using it:** [Start a discussion](../../discussions)
- **Questions or ideas:** [Discussions board](../../discussions)

If something doesn't work the way you expect, or a skill produces bad output, please open an issue with what you tried and what happened. Real examples help the most.

**Get in touch:** [arezou@solouki.se](mailto:arezou@solouki.se) | [LinkedIn](https://www.linkedin.com/in/arezousolouki/) | [solouki.se](https://solouki.se/)

## License

MIT License. See [LICENSE](LICENSE).
