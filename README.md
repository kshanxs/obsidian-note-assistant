<div align="center">

<br>

# ✦ obsidian-note-assistant ✦

### *Your AI-Powered Second Brain*

*Draft → Refine → Graph-Link → Sync — with a protected private vault the AI can never touch*

<br>

[![Version](https://img.shields.io/badge/version-1.0.0-8957e5?style=for-the-badge&labelColor=161b22)](./docs/USAGE.md)
[![Install](https://img.shields.io/badge/⚡_Install-npx_skills_add-0d1117?style=for-the-badge&labelColor=161b22)](https://github.com/kshanxs/obsidian-note-assistant)
[![License](https://img.shields.io/badge/License-MIT-2ea043?style=for-the-badge&labelColor=161b22)](./LICENSE)
[![Docs](https://img.shields.io/badge/Docs-USAGE.md-f78166?style=for-the-badge&labelColor=161b22)](./docs/USAGE.md)

<br>

*Three folders. Graph-linked notes. Native CLI support. Your drafts stay yours, the AI organizes, and your private vault stays private — always.*

</div>

---

## 🚀 Installation

```bash
npx skills add kshanxs/obsidian-note-assistant
```

### Update to latest version

```bash
npx skills update kshanxs/obsidian-note-assistant
```

---

## 🗂️ Vault Structure

```
YourVault/
├── Drafts/           ← You write here. AI reads only, never rewrites.
│   └── README.md
├── AI Notes/         ← AI writes here. Graph-linked and auto-categorized.
│   ├── README.md
│   ├── Ideas/Coding/
│   ├── Ideas/Book/
│   ├── Ideas/Trip/
│   ├── Daily/
│   ├── Knowledge/
│   └── Projects/
└── Secure Vault/     ← 🔒 AI-free zone. Never read. Never written. Ever.
    └── README.md
```

Each folder includes a `README.md` explaining what belongs there and how the AI interacts with it.

---

## 💬 Quick Start

```
"Set up my Obsidian vault"                    → initializes structure, backs up existing notes
"Here's a rough draft — process it"          → creates a new graph-linked AI note
"Sync my draft with its AI note"             → merges changes from both sides
"I just learned something, add it to my brain" → creates a Knowledge note
```

**→ [Full usage guide with examples](./docs/USAGE.md)**

---

## ✨ Highlights

| | |
|---|---|
| 🚀 **Vault Initialization** | Detects existing notes, auto-backs up, then sets up 3-folder structure |
| 📝 **Smart Draft Processing** | Turns raw messy drafts into clean structured AI notes |
| 🕸️ **Graph View Wikilinks** | Every AI note includes wikilinks — appears connected in Obsidian's Graph View |
| 🔄 **Bidirectional Sync** | Merges changes from both draft and AI note without losing anything |
| 🔒 **Secure Vault** | A folder hardcoded as off-limits to the AI — for truly private notes |
| 🖥️ **Obsidian CLI Support** | Outputs native `obsidian create/read/prepend/move` commands + shell fallback |
| 🏷️ **Refined ID System** | Permanent IDs linking every draft to its AI note across syncs |
| 🗂️ **Folder READMEs** | Each folder ships with a README explaining how it works |

---

## ⚡ Command Reference

| Say this | What happens |
|---|---|
| `"Set up my vault"` or `"Initialize"` | Backs up existing notes, creates 3-folder structure |
| `"Here's my draft, process it"` | **Create** — new graph-linked AI note in `AI Notes/` |
| `"Sync my draft and AI note"` | **Sync** — merges both sides bidirectionally |
| `"Improve this AI note"` | **Enhance** — polishes quality without changing meaning |
| `"Add this to my second brain"` | Creates a note from raw pasted text |
| `"What links to this note?"` | Runs `obsidian backlinks path="..."` |

---

## 🖥️ Obsidian CLI Integration

The skill outputs native Obsidian CLI commands for every file operation, with shell fallbacks. Requires Obsidian ≥ 1.11.7 with CLI enabled (Settings → General → Command line interface).

```bash
# Create an AI note
obsidian create path="AI Notes/Ideas/Coding/2026-03-19 - My App.md" content="..." overwrite

# Read a draft
obsidian read path="Drafts/my-draft.md"

# Prepend sync header to draft
obsidian prepend path="Drafts/my-draft.md" content="---\nstatus: refined\n..."

# Move a note into the new structure
obsidian move path="_backup/old-note.md" to="Drafts/"

# Check backlinks
obsidian backlinks path="AI Notes/Knowledge/Atomic Habits Chapter 3.md"
```

---

## 🕸️ Graph View

Every AI note is built to be a rich graph node:
- **`aliases:`** in frontmatter — find the note under multiple names
- **Inline wikilinks** — links to related topics, people, books, projects
- **`## Related Notes`** section — dedicated outgoing links
- **Bidirectional links** — draft ↔ AI note both wikilink each other

Unresolved links (notes that don't exist yet) show as hollow nodes — a visual map of ideas yet to be explored.

---

## 📁 Skill Structure

```
obsidian-note-assistant/
├── SKILL.md
├── references/
│   ├── categories.md           ← When to use each of the 6 note categories
│   ├── note_template.md        ← Templates for all 6 note types (with wikilinks)
│   └── vault-init.md           ← Backup + vault initialization flow
├── assets/
│   └── folder-readmes/
│       ├── Drafts-README.md
│       ├── AI-Notes-README.md
│       └── Secure-Vault-README.md
└── evals/
    └── evals.json
```

---

## 🔒 About the Secure Vault

Hard boundary built into the skill — not a setting. The AI will never:
- Read or write files inside it
- Reference its contents in other notes
- Accept instructions to access it, even if you ask

---

## 📝 Changelog

### v1.0.0 — 2026-03-19
- **Initial Release**: Complete Obsidian note assistant with Create, Sync, and Enhance modes.
- **Vault Init**: New initialization flow — detects existing notes, auto-creates timestamped backup, and sets up robust 3-folder structure (`Drafts/`, `AI Notes/`, `Secure Vault/`).
- **Graph View**: Every AI note natively supports Obsidian's graph view with `aliases`, inline wikilinks, and `## Related Notes` sections. 
- **Obsidian CLI**: Full command-line integration utilizing native Obsidian CLI commands + shell fallbacks.
- **Secure Vault**: Protected environment the AI is strictly hardcoded to never access.

---

<div align="center">

## 📄 License

MIT © [Shubhanshu](https://github.com/kshanxs)

*Built for thinkers who want their notes to grow with them.*

</div>
