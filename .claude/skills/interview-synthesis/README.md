# /interview-synthesis

Turn raw customer interview notes into structured themes, findings, and recommendations.

## How to use it

Type `/interview-synthesis` followed by the topic area:

```
/interview-synthesis onboarding
/interview-synthesis checkout flow
```

Provide interview notes in one of two ways:
- Place transcripts in `context/interviews/` before running
- Paste notes directly into the conversation when prompted

## What you get

A synthesis document saved to `output/` (e.g., `interview-synthesis-onboarding.md`). It includes:

- Themes and patterns across participants
- Signal strength labels (pattern = 3+ mentions, anecdote = 1-2)
- Direct quotes supporting each finding
- A "Contradictions & Outliers" section flagging where findings might be wrong

## Tips

- The skill explicitly flags confirmation bias. If all findings point one direction, it will call that out.
- Fill in `context/personas.md` first so findings can be mapped to real user segments.
- When you're happy with a synthesis, say "finalize this" to move it to `context/interviews/`.
