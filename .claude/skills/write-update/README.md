# /write-update

Write a status update for a project or initiative, matched to the right audience and format.

## How to use it

Type `/write-update` followed by the project name:

```
/write-update search redesign
/write-update Q1 roadmap
```

You can specify the audience or let it ask. It picks from three styles:

- **Executive briefing** ("exec update", "board update") — numbers-first, decision-oriented
- **Slack update** ("team update", "quick update") — short, scannable
- **Notion document** ("full update", "detailed update") — comprehensive write-up

## What you get

A markdown document saved to `output/` (e.g., `update-search-redesign.md`). It pulls from your context files and any existing specs for the project.

## Tips

- Have current status or metrics ready. It will ask rather than guess.
- Fill in `context/company.md` and `context/product.md` first for better grounding.
- It checks `context/specs/` for related artifacts to reference.
