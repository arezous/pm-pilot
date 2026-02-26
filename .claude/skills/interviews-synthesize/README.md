# /interviews-synthesize

Turn customer interview notes into themes, recommendations, and a standalone pain points document.

## How to use it

Type `/interviews-synthesize` followed by the topic area:

```
/interviews-synthesize onboarding
/interviews-synthesize checkout flow
/interviews-synthesize all
```

Provide interview notes in one of two ways:
- Place them in `output/interviews/` before running
- Paste notes directly into the conversation when prompted

You can scope by topic, persona, date range, or include everything.

## What you get

Two documents saved to `output/interviews/`:

1. **Synthesis report** (`synthesis-[topic]-[YYYY-MM-DD].md`) — themes with frequency, severity, supporting quotes, Jobs-to-be-Done framing, and specific recommendations.
2. **Pain points document** (`pain-points-[topic]-[YYYY-MM-DD].md`) — problems only, no solutions. Evidence base for future specs.

## Tips

- Flags unreliable signals (hypotheticals, future predictions, vague praise) and excludes them from themes.
- Themes require 2+ customers. Single-customer observations go in the appendix.
- Checks for previous synthesis on the same topic and builds on it.
- Pair with `/spec-write` to turn top themes into feature specs, or `/status-update` for a stakeholder summary.
- Say "finalize this" to move files to `context/interviews/`.
