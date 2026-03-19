# Note Template Reference

This file contains templates for each note category. Use the appropriate template based on the category.

## Graph View — How to apply wikilinks

Every AI note should include wikilinks to make it a connected node in Obsidian's Graph View:
- `[[Other Note Name]]` — link to any related note (existing or future)
- `aliases:` in frontmatter — lets this note be found under alternate names
- `## Related Notes` at the bottom — reserved section for all outgoing connections
- Both the `draft_source` and any topic mentions should be wikilinked

Future notes (not yet created) show as hollow nodes in the graph — use them freely to map what you plan to explore.

---

## Template: Ideas/Coding

```markdown
---
title: "<Title>"
aliases: ["<Short Name>", "<Alt Name>"]
tags: [#idea, #coding, <additional-tags>]
category: Ideas/Coding
refined_id: RID-YYYYMMDD-XXXX
draft_source: "[[Drafts/<Draft Filename>]]"
created: YYYY-MM-DD
last_synced: YYYY-MM-DD
---

# <Title>

## Idea Description
<What is this? Explain clearly in 2–4 sentences. What problem does it solve or what makes it interesting?>

## Key Features
- <Feature 1>
- <Feature 2>
- <Feature 3>

## Tech Stack / Approach *(optional)*
<Languages, frameworks, APIs, architecture notes — link to [[relevant tools]] or [[frameworks]]>

## Why It Matters
<Why is this idea worth building? What's the motivation or insight behind it?>

## Open Questions
- <Unresolved design or technical question>

## Next Steps
- [ ] <First action to take>
- [ ] <Second action>

## Related Notes
- [[<Related Project or Idea>]]
- [[<Related Tool or Concept>]]
```

---

## Template: Ideas/Book

```markdown
---
title: "<Title>"
aliases: ["<Short Name>", "<Genre> Novel Idea"]
tags: [#idea, #writing, #book, <genre-tags>]
category: Ideas/Book
refined_id: RID-YYYYMMDD-XXXX
draft_source: "[[Drafts/<Draft Filename>]]"
created: YYYY-MM-DD
last_synced: YYYY-MM-DD
---

# <Title>

## Concept
<The core premise or idea. What is this story/book about at its heart?>

## Setting
<World, time period, location — as much as is known — link to [[Place Name]] if detailed>

## Characters *(if any)*
- **[[<Character Name>]]**: <Brief description>

## Themes
<Central themes — link to [[Theme Note]] if explored elsewhere>

## Plot Sketch *(optional)*
<Rough arc or key story beats, if known>

## Notes / Fragments
<Raw ideas, dialogue snippets, images — things that don't fit neatly elsewhere>

## Next Steps
- [ ] <Develop character X>
- [ ] <Outline Act 1>

## Related Notes
- [[<Related Book Idea or Character>]]
- [[<Inspiration Source>]]
```

---

## Template: Ideas/Trip

```markdown
---
title: "<Destination> — <Trip Type>"
aliases: ["<Destination> Trip", "<Month Year> <Destination>"]
tags: [#trip, #travel, <destination-tag>]
category: Ideas/Trip
refined_id: RID-YYYYMMDD-XXXX
draft_source: "[[Drafts/<Draft Filename>]]"
created: YYYY-MM-DD
last_synced: YYYY-MM-DD
---

# <Destination> — <Trip Type>

## Overview
<When, where, who. What kind of trip — link to companions if they have notes: [[Person Name]]>

## Key Details
- **Duration:** <X days>
- **Estimated Budget:** <amount>
- **Travel Dates:** <if known>
- **Companions:** [[<Person 1>]], [[<Person 2>]]

## Places to Visit / Things to Do
- [[<Place 1>]] — <notes>
- [[<Place 2>]] — <notes>

## Logistics
- **Getting there:** <flight/train/drive info>
- **Accommodation:** <hotel/hostel/Airbnb ideas>
- **Packing notes:** <anything specific to pack>

## Next Steps
- [ ] Research accommodation options
- [ ] Book transport

## Related Notes
- [[<Previous Trip to Same Destination>]]
- [[<Related Travel Resource>]]
```

---

## Template: Daily

```markdown
---
title: "Daily — YYYY-MM-DD"
aliases: ["Journal YYYY-MM-DD", "<Day of Week> <Date>"]
tags: [#daily, #journal]
category: Daily
refined_id: RID-YYYYMMDD-XXXX
draft_source: "[[Drafts/<Draft Filename>]]"
created: YYYY-MM-DD
---

# Daily — YYYY-MM-DD

## What Happened
<Key events, conversations — link to [[People]], [[Projects]], or [[Places]] mentioned>

## What I Learned
<Something new — link to [[Knowledge Note]] if you want to explore it further>

## Reflection
<How am I feeling? What's on my mind? Any patterns I'm noticing?>

## Gratitude *(optional)*
- <One thing I'm grateful for>

## Tomorrow
<Intentions, tasks — link to [[Project Name]] if relevant>

## Related Notes
- [[Daily — <Yesterday's date>]]
- [[<Any note referenced today>]]
```

---

## Template: Knowledge

```markdown
---
title: "<Topic>"
aliases: ["<Short Name>", "<Alt Phrasing>"]
tags: [#knowledge, <topic-tags>]
category: Knowledge
refined_id: RID-YYYYMMDD-XXXX
draft_source: "[[Drafts/<Draft Filename>]]"
created: YYYY-MM-DD
last_synced: YYYY-MM-DD
---

# <Topic>

## Summary
<What is this? 2–4 sentences a future-you understands quickly — link to [[Source Book/Article]]>

## Key Concepts
- **[[<Concept 1>]]**: <explanation>
- **[[<Concept 2>]]**: <explanation>

## My Take
<Personal interpretation — link to [[Related Idea or Project]] where you'd apply this>

## Open Questions
<Things still unsure about — these become hollow nodes in the graph>

## Sources / References *(optional)*
- [[<Book or Article Name>]]
- [<External URL Title>](<URL>)

## Related Notes
- [[<Related Knowledge Note>]]
- [[<Project where this applies>]]
```

---

## Template: Projects

```markdown
---
title: "<Project Name>"
aliases: ["<Short Project Name>", "<Acronym if any>"]
tags: [#project, <domain-tags>]
category: Projects
refined_id: RID-YYYYMMDD-XXXX
draft_source: "[[Drafts/<Draft Filename>]]"
created: YYYY-MM-DD
last_synced: YYYY-MM-DD
status: active
---

# <Project Name>

## Overview
<What is this project? What does it accomplish?>

## Goals
- <Goal 1 — specific and measurable>
- <Goal 2>

## Tasks
- [ ] <Task 1>
- [ ] <Task 2>
- [x] <Completed task>

## Timeline *(optional)*
| Milestone | Target Date |
|---|---|
| [[<Linked Milestone Note>]] | YYYY-MM-DD |

## Notes
<Decisions made, blockers, ideas — link to [[Relevant Knowledge]] or [[Related Ideas]]>

## Status
<Current state in 1–2 sentences>

## Related Notes
- [[<Core Idea this Project came from>]]
- [[<Related Knowledge or Research>]]
- [[<Daily Note where this was discussed>]]
```
