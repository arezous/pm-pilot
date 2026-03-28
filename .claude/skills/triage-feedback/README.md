# /triage-feedback

Categorize, prioritize, and route incoming customer feedback so you stop firefighting and start pattern-matching.

## How to use it

Type `/triage-feedback` followed by the feedback or topic:

```
/triage-feedback [paste support tickets]
/triage-feedback this week's app reviews
/triage-feedback data/feedback/march-nps-comments.csv
```

Accepts: support tickets, survey responses, app reviews, Slack messages, emails, or any raw customer feedback. Paste it directly or point to files in `data/feedback/`.

## What you get

A triaged report saved to `output/feedback/` with:

- **Categorized items** -- bugs, feature requests, complaints, praise, questions
- **Priority ranking** -- by severity, frequency, and alignment with current priorities
- **Patterns** -- recurring themes across feedback items
- **Routing suggestions** -- which team or person should handle each category
- **Persona mapping** -- which personas are most affected

## Tips

- Fill in `context/product.md` (what's shipped, what's broken) and `context/personas.md` first for better routing and pattern detection.
- Drop raw feedback files in `data/feedback/` before running for batch processing.
- Pain points and patterns can update `context/personas.md` with your approval.
- Pair with `/prioritize` to score the top feature requests against your roadmap.
- Pair with `/prd` to spec out the most requested features.
- Say "finalize this" to move the triage to `context/feedback/`.
