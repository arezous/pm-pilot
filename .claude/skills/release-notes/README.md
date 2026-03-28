# /release-notes

Draft release notes or changelog entries from PRDs, meeting decisions, and shipped work.

## How to use it

Type `/release-notes` followed by the release name or version:

```
/release-notes v2.3
/release-notes March release
/release-notes [paste what shipped]
```

Accepts: pasted descriptions of what shipped, file paths to specs, or references to workspace files ("the search PRD", "last sprint's meeting notes").

## What you get

User-facing release notes saved to `output/` (e.g., `release-notes-v2.3-2026-03-28.md`). Written for users, not engineers. Focuses on what changed and why it matters, not how it was built.

## Tips

- It scans `output/prd/`, `context/prd/`, `output/meetings/`, and `context/meetings/` for recent shipped work automatically.
- Give it the audience: "release notes for users", "changelog for developers", "update for the sales team."
- Pair with `/status-update` to include the release in stakeholder communications.
- Works best when PRDs exist for the shipped features. More input context = better notes.
