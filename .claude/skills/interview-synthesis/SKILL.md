---
name: interview-synthesis
description: Synthesize customer interview notes into themes, findings, and recommendations.
argument-hint: [topic]
---

Synthesize customer interviews on: $ARGUMENTS

Follow this workflow:

1. Read all files in `context/` — especially `context/personas.md` and `context/product.md` for grounding.
2. Read `template/interview-synthesis.md` as your starting structure.
3. Ask the user to provide interview notes or transcripts if not already shared.
4. Identify themes, patterns, and contradictions across participants.
5. Be opinionated: rank findings by signal strength and make concrete recommendations.
6. Include direct quotes to support each finding.
7. Save the output to `output/interview-synthesis-$ARGUMENTS.md` (use kebab-case for the filename).
