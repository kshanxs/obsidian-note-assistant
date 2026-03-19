# 🤖 AI Notes

This folder is **managed by the AI assistant**. Every note here was generated or updated from a draft in the `Drafts/` folder.

## What goes here
- Refined, structured versions of your draft notes
- Organized by category into subfolders
- Clean, scannable Obsidian-ready markdown

## Folder structure
```
AI Notes/
├── Ideas/
│   ├── Coding/      ← App ideas, dev projects, technical concepts
│   ├── Book/        ← Story ideas, characters, plot outlines
│   └── Trip/        ← Travel plans, itineraries, destination notes
├── Daily/           ← Daily reflections, journal entries
├── Knowledge/       ← Book summaries, learning notes, research
└── Projects/        ← Active projects with tasks and timelines
```

## How notes are created here
1. You write a draft in `Drafts/`
2. You ask the AI to process it
3. The AI generates a refined note in the right subfolder
4. The note links back to the original draft via a `draft_source` frontmatter field

## Can I edit notes here?
Yes! The AI will preserve your manual edits the next time you sync. When you sync, the AI:
- Keeps everything you've added or improved
- Merges new ideas from the draft without duplicating
- Never deletes anything

## Note naming format
All AI-generated notes follow this format:
```
YYYY-MM-DD - <Descriptive Title>.md
```

## Frontmatter
Every AI note includes:
```yaml
---
title: "..."
tags: [#category, #topic]
category: Ideas/Coding
refined_id: RID-YYYYMMDD-XXXX     ← links to the source draft
draft_source: "[[Drafts/...]]"
created: YYYY-MM-DD
last_synced: YYYY-MM-DD
---
```
