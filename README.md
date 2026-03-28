# PM Operating System

Your AI-powered copilot for modern product management. Built for Claude Code, Cursor, and Codex.

## Philosophy

Most PMs use AI the same way they use Google: one-off questions, zero context. This system works differently. You build context about your company, competitors, personas, and product. Every skill draws from that context so outputs are grounded in your actual world, not generic advice.

## Project Structure

```
pmos-starterkit/
├── context/           # What you know (living documents)
│   ├── company.md     # Who you are, goals, constraints
│   ├── competitors.md # Competitive landscape summary
│   ├── personas.md    # Who you serve, their needs
│   └── product.md     # What you have, what works
├── data/              # Raw source material (transcripts, exports, dumps)
├── template/          # Output formats and style guides
├── output/            # Drafts and generated artifacts
└── setup/             # Environment configuration
```

Drafts land in `output/`. When finalized, they move to `context/` subfolders (e.g., `context/prd/`, `context/interviews/`). Folders are created as the work requires them.

## Skills

| Command | What it does |
|---|---|
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

## Getting Started

**Requires [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Cursor](https://www.cursor.com/), or Codex.**

1. Clone this repository
2. Open it in Claude Code, Cursor, or Codex
3. Run `/onboard` to set up your context files, or just start talking about your company and product
4. The system will guide you from there

You don't need to fill everything in before you start. Skills work with whatever context exists and ask you directly when something is missing.

## Using PM Pilot in Codex

In Codex, type the same PM Pilot command names at the start of your message:

- `/onboard`
- `/prd`
- `/analyze-competitors`
- `/product-teardown`
- `/synthesize-interviews`
- `/meeting-notes`
- `/status-update`
- `/prioritize`
- `/triage-feedback`
- `/break-down`
- `/release-notes`
- `/critique`

This is command-name parity in chat. It does not imply native slash-command registration.

## Flexible Input

You can feed information to any skill three ways:

- **Paste it** directly in the conversation (transcript, requirements, feedback, etc.)
- **Drop a file path** into the terminal (drag a file in, the skill reads it automatically)
- **Reference a workspace file** by name (e.g., "use the search PRD", "synthesize last week's interviews")

External files (like `~/Downloads/interview-notes.md`) are processed immediately. The skill will offer to save them to the workspace for future use.

## Feedback and Issues

This is an early release. Your feedback makes it better.

- **Report bugs or suggest features:** [Open an issue](../../issues)
- **Share how you're using it:** [Start a discussion](../../discussions)
- **Questions or ideas:** [Discussions board](../../discussions)

If something doesn't work the way you expect, or a skill produces bad output, please open an issue with what you tried and what happened. Real examples help the most.

**Get in touch:** [arezou@solouki.se](mailto:arezou@solouki.se) | [LinkedIn](https://www.linkedin.com/in/arezousolouki/) | [solouki.se](https://solouki.se/)
