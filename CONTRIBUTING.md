# Contributing to PM Pilot

Thanks for your interest in contributing. This guide covers what you need to know.

## What this repo is

PM Pilot is a Claude Code workspace for product managers. It ships skills (AI workflows), templates, and a context system. Users clone it and fill in their own product context locally.

**What gets committed:** skills, templates, CLAUDE.md, AGENTS.md, README, and structural files.

**What stays local (gitignored):** context files (`context/company.md`, etc.), `data/`, `output/`, and `.claude/settings.local.json`. These contain user-specific product data and should never be committed.

## Repo structure

```
.claude/
  skills/           # Each skill is a folder with SKILL.md + README.md
  settings.local.json  # Local only (gitignored)
context/            # User's product context (gitignored, ships with headers only)
data/               # Raw inputs like transcripts (gitignored)
output/             # Generated drafts (gitignored)
template/           # Output format templates
  styles/           # Audience-specific style templates
CLAUDE.md           # System instructions (project-level)
AGENTS.md           # Agent instructions (for Codex, Cursor, etc.)
README.md           # User-facing docs
```

## What to contribute

- Bug fixes in skills
- Skill improvements (better prompts, workflow steps, quality rules)
- New skills that solve a real PM problem
- Template improvements or new output templates
- Style templates for specific audiences (board updates, Slack, Notion)
- Documentation fixes
- LLM compatibility (Cursor, Windsurf, Codex) that doesn't break Claude Code

## How to contribute

### Adding or improving a skill

Each skill lives in `.claude/skills/<skill-name>/` and contains two files:

**SKILL.md** - the workflow definition. Structure:

```yaml
---
name: skill-name
version: x.y.z
description: One-line description of what the skill does.
argument-hint: e.g. "example input"
---
```

Followed by:
- Role statement (one line, who the AI acts as)
- Source and destination (where input comes from, where output goes)
- Workflow steps (the process, 40-100 lines ideally)
- Quality rules (constraints on the output)

**README.md** - user-facing documentation. Explains what the skill does, when to use it, example prompts, and what output to expect.

**Conventions:**
- Skills read context files before producing output. If context is missing, they flag it.
- Output goes to `output/`. Approved output moves to `context/` subfolders.
- Every output doc must include a `**Status:** Draft` field in its header. When the user approves it, the skill updates the status and moves it to the matching `context/` subfolder (e.g., `context/prd/`, `context/competitors/`).
- Templates in `template/` define output formats. Reference them in SKILL.md. If your skill produces a new output type, add a template for it in `template/`.
- If your skill's output feeds into another skill (e.g., `/analyze-competitors` output used by `/prioritize`), note that in the SKILL.md and test that the downstream skill still works.
- Keep SKILL.md focused on process. Move large reference material to `reference/` subfolders if needed.
- Follow semantic versioning for skill versions.

**When adding a new skill, also update:**
- The skills table in `README.md`
- The command list in `AGENTS.md`

### Adding or improving a template

Templates live in `template/`. They define the structure and sections of a specific output type (e.g., `competitive-deep-dive.md`, `product-teardown.md`).

Audience-specific style templates live in `template/styles/` (e.g., `executive-briefing.md`, `investor-update.md`).

Templates should be structural, not prescriptive. Define sections and what belongs in each, not filler text.

**Template-skill relationship:** Most skills reference a template. If you're adding a skill that produces a new output type, create a matching template. If an existing template fits, reference it rather than creating a duplicate. Check `template/` before adding anything new.

### Improving context file headers

The repo ships empty context files (`context/company.md`, `context/competitors.md`, etc.) with just section headings. These headers are committed. The filled-in content is gitignored. If you're improving the header structure or default sections, that's a valid contribution. Don't add example content that looks like real product data.

### Improving CLAUDE.md or AGENTS.md

These files affect every conversation. **Open an issue before changing them.**

- `CLAUDE.md` contains system-level instructions. Keep it under 200 lines. Every line should prevent a mistake the AI would otherwise make.
- `AGENTS.md` is a lighter version for non-Claude Code environments (Codex, Cursor). Keep it in sync with CLAUDE.md but shorter.

## Writing style

The repo follows these rules (and so should contributions):

- Short, specific, actionable
- Use real examples over abstract descriptions
- No em dashes. Use commas, periods, or parentheses.
- Avoid: "delve," "leverage," "utilize," "unlock," "harness," "streamline," "robust," "cutting-edge"
- Sound human. Vary sentence length. Use contractions.

## Important: no product data

Files in `context/`, `data/`, and `output/` are gitignored because they contain user-specific product data. Before submitting a PR:

- **Never commit context files, competitive analyses, or interview data**
- **Check `git diff`** to make sure no product info slipped in
- **Examples use generic names** (Acme Corp, not real companies)

A PR with real product data will be closed immediately.

## Versioning

Each skill has a version in its SKILL.md frontmatter. If your change modifies skill behavior:

- **Bug fix** (output format, typo in prompt): patch bump (1.0.0 -> 1.0.1)
- **Improved behavior** (better workflow, new quality rules): minor bump (1.0.0 -> 1.1.0)
- **New mode or breaking change**: major bump (1.0.0 -> 2.0.0)

## Pull request process

1. Fork the repo and create a branch (`fix/skill-name` or `feature/skill-name`)
2. Make your changes
3. Test the skill or template by actually running it in Claude Code (or Cursor/Codex)
4. Write a clear PR description: what you changed and why
5. One skill per PR unless changes are tightly coupled

### What makes a good PR

- Solves a real problem or fills a gap a PM would hit
- Includes a README if adding a new skill
- Tested with real inputs, not just read for correctness
- Doesn't introduce gitignored files (context, data, output)

### What to avoid

- PRs that only add comments or docstrings without functional changes
- Generic skills that could apply to any profession (keep it PM-specific)
- Changes to gitignored files (context/, data/, output/)
- Large refactors without discussion first (open an issue)

## Running and testing locally

1. Install [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
2. Clone the repo
3. Open it in Claude Code, Cursor, or Codex
4. Run `/onboard` to populate your local context files (skills depend on context to produce good output)
5. Test your changes by running the skill with real inputs

**How to test a skill:**

Skills produce different output depending on what context exists. Always populate context files before testing.

1. Run `/onboard` and fill in at least company and product context
2. Run the skill with a realistic prompt (e.g., `/analyze-competitors Linear`, `/prd user onboarding flow`)
3. Check that the output follows the matching template format
4. Check that the output includes `**Status:** Draft`
5. If the skill chains with others (e.g., output feeds `/prioritize`), test that too

## Reporting issues

- **Bugs:** open an issue with what you tried, what happened, and what you expected
- **Skill output quality:** include the prompt you used and the output you got
- **Feature ideas:** open an issue describing the PM problem it solves

## Questions?

Open a [discussion](../../discussions) or email [arezou@solouki.se](mailto:arezou@solouki.se).

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
