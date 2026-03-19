# Usage Guide — obsidian-note-assistant

---

## Setting Up Your Vault

Create this structure in Obsidian, and drop the matching README into each folder:

```
YourVault/
├── Drafts/
│   └── README.md               ← copy from assets/folder-readmes/Drafts-README.md
├── AI Notes/
│   ├── README.md               ← copy from assets/folder-readmes/AI-Notes-README.md
│   ├── Ideas/Coding/
│   ├── Ideas/Book/
│   ├── Ideas/Trip/
│   ├── Daily/
│   ├── Knowledge/
│   └── Projects/
└── Secure Vault/
    └── README.md               ← copy from assets/folder-readmes/Secure-Vault-README.md
```

---

## The Three Folders

### 📝 Drafts/
Your raw writing space. Write anything, exactly as it comes to mind. The AI reads your drafts but **never modifies the content** — it only adds a small sync header at the very top when a draft has been processed.

### 🤖 AI Notes/
Everything the AI generates lives here. Organized into 6 categories automatically. You can manually edit notes here — the AI will preserve your changes on the next sync.

### 🔒 Secure Vault/
Completely private. The AI will never open, read, or write to any file here. Use this for personal reflections, sensitive info, or anything you want to keep fully private.

---

## The Three Modes

### Create Mode
**Trigger:** You give the AI only a draft.

The AI reads the draft, picks the right category, and generates a full refined note in `AI Notes/`.

```
"Here's a rough draft — turn it into an Obsidian note:
[paste your draft]"

"Add this to my second brain: I've been thinking about..."
```

**Output:**
1. Complete AI note (save to `AI Notes/...`)
2. Sync header (prepend to your draft in `Drafts/`)
3. Shell commands to write both

---

### Sync Mode
**Trigger:** You give the AI both a draft AND its existing AI note.

The AI compares both, merges new content from the draft into the AI note, preserves manual edits in the AI note, and updates both sync headers.

```
"I've added new ideas to my draft. Here's both versions:
[paste draft]
[paste AI note]"
```

**What the AI checks:**
- Are the Refined IDs matching? (if not, it stops and warns you)
- What's new in the draft → added to AI note
- What was manually improved in AI note → kept and enhanced
- Conflicts → both versions preserved with a note

---

### Enhance Mode
**Trigger:** You share an AI note and ask for improvements.

```
"This AI note is a bit rough — can you clean it up?"
"Restructure this without changing the content."
```

---

## The Refined ID System

When a draft is first processed, both notes get a `refined_id` like `RID-20260319-F2A1`.

- In the draft: `refined_id:` in the frontmatter header
- In the AI note: `refined_id:` in the frontmatter

This ID never changes. It's how the AI knows which notes belong together — even if you rename files.

**Don't delete the Refined ID.**

---

## Note Categories

| Category | Folder | Best for |
|---|---|---|
| Coding Idea | `AI Notes/Ideas/Coding/` | App concepts, dev projects, tech ideas |
| Book Idea | `AI Notes/Ideas/Book/` | Story concepts, characters, plot |
| Trip Idea | `AI Notes/Ideas/Trip/` | Travel plans, itineraries |
| Daily | `AI Notes/Daily/` | Journal entries, daily reflections |
| Knowledge | `AI Notes/Knowledge/` | Book summaries, learning notes |
| Project | `AI Notes/Projects/` | Active projects with tasks |

→ [Full category guide](../obsidian-note-assistant/references/categories.md)

---

## Vault Commands (Shell)

Every response includes shell commands. Replace `/path/to/vault/` with your vault path:

```bash
# macOS common vault locations:
~/Documents/MyVault/
~/Library/Mobile Documents/iCloud~md~obsidian/Documents/MyVault/

# Example:
cat > "/path/to/vault/AI Notes/Ideas/Coding/2026-03-19 - My App.md" << 'EOF'
[note content]
EOF
```

---

## Tips

- **Draft messily** — don't clean up before processing; the AI handles the structure
- **Sync regularly** — smaller diffs mean cleaner merges
- **Use Secure Vault liberally** — anything you're unsure about, keep it private
- **Don't rename drafts** after syncing — the Refined ID system handles linking, but consistent filenames help you find things
