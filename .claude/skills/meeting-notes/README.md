# /meeting-notes

Transform meeting transcripts, voice memos, or raw notes into structured decisions, action items, and insights.

## How to use it

Type `/meeting-notes` followed by your content:

```
/meeting-notes                              → I'll ask for your content
/meeting-notes [paste transcript]           → Process immediately
/meeting-notes [paste notes] --minimal      → Quick-capture format
/meeting-notes [paste notes] --slack        → Slack-friendly format
```

Accepts: Zoom/Otter/Grain transcripts, bullet-point notes, voice memo dictation, Slack threads, email chains, or just "tell me what happened."

## What you get

A structured document saved to `output/meetings/` (e.g., `2026-02-26-roadmap-review.md`) with:

- **Decisions made** with rationale and owners
- **Action items** with owners, due dates, and priority
- **Key insights and quotes** (verbatim from transcript)
- **Open questions** with owners to resolve them
- **Blockers** and how to unblock them
- **Next steps** with timeline

Output adapts to meeting type: customer interviews get quotes and validation status, stakeholder reviews lead with decisions, team syncs focus on action items.

## Tips

- Process meetings within 24 hours while context is fresh.
- Include who was there so action items get assigned correctly.
- For long transcripts (90+ min), it offers to focus on key segments.
- Detects timeline conflicts against existing PRDs and previous meetings.
- Flags when an "A/B test" decision is missing experiment design details.
- Pair with `/interviews-synthesize` after 3+ customer interviews on the same topic.
- Pair with `/prd` to turn meeting decisions into feature specs.
- Pair with `/status-update` to include meeting outcomes in stakeholder updates.
- Say "finalize this" to move notes to `context/meetings/`.
