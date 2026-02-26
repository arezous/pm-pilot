# /interview-synthesis

Turn customer interview notes into actionable themes, prioritized recommendations, and a standalone pain points document for PRD writing.

## How to use it

Type `/interview-synthesis` followed by the topic area:

```
/interview-synthesis onboarding
/interview-synthesis checkout flow
/interview-synthesis all
```

Provide interview notes in one of two ways:
- Place them in `output/interviews/` before running
- Paste notes directly into the conversation when prompted

You can scope by topic, persona, date range, or include everything.

## What you get

Two documents saved to `output/interviews/`:

1. **Synthesis report** (`synthesis-[topic]-[YYYY-MM-DD].md`) — themes clustered from observations, each with frequency, severity, supporting quotes, Jobs-to-be-Done framing, and a specific recommendation. Includes an executive summary, contradictions section, and research gaps.

2. **Pain points document** (`pain-points-[topic]-[YYYY-MM-DD].md`) — problems only, no solutions. Serves as the evidence base for future PRD writing.

## Moving to context

Everything starts in `output/`. When you're happy with the results, say "finalize this" or "move this to context" and Claude will move the files to `context/interviews/`. Once there, they become part of the knowledge base that all other skills draw from.

## Tips

- It flags unreliable signals (hypotheticals, future predictions, vague praise) and excludes them from themes.
- Themes require 2+ customers. Single-customer observations go in the appendix, not the findings.
- It checks for previous synthesis on the same topic and builds on it rather than duplicating.
