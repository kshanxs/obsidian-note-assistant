# Vault Initialization & Backup Flow

This file contains the exact steps the AI runs when setting up a new vault or migrating an existing one.

---

## Step 1 — Detect existing content

First, check if the vault already has notes:

```bash
# Obsidian CLI
obsidian folders
obsidian files

# Shell
ls "/path/to/vault/"
```

**Decision tree:**
- No markdown files found → go to **Step 3** (fresh setup)
- Markdown files found outside the 3-folder structure → go to **Step 2** (backup + migrate)
- Already has `Drafts/`, `AI Notes/`, `Secure Vault/` → go to **Step 4** (verify + repair)

---

## Step 2 — Backup existing notes

**Never restructure without backing up first.**

The AI automatically creates a timestamped backup folder. Tell the user what it's doing before running commands.

### Announce to the user:
> "I found existing notes in your vault. I'll back them all up to `_backup_YYYYMMDD_HHMMSS/` before setting up the new structure. Your originals are safe — nothing will be deleted."

### Backup command (shell — most reliable for bulk copy):
```bash
# Create backup with timestamp
BACKUP_DIR="_backup_$(date +%Y%m%d_%H%M%S)"
mkdir -p "/path/to/vault/$BACKUP_DIR"
cp -r "/path/to/vault/"*.md "/path/to/vault/$BACKUP_DIR/" 2>/dev/null
cp -r "/path/to/vault/"/[^._]*/ "/path/to/vault/$BACKUP_DIR/" 2>/dev/null
echo "✅ Backup created at: $BACKUP_DIR"
```

### Verify backup:
```bash
# Count files backed up
find "/path/to/vault/$BACKUP_DIR" -name "*.md" | wc -l
```

Tell the user: "X notes backed up. You can find them in `_backup_YYYYMMDD/` any time."

---

## Step 3 — Create the 3-folder structure

Create all required folders and drop in the README files from `assets/folder-readmes/`.

### Obsidian CLI:
```bash
# Create folders (by creating placeholder files — Obsidian doesn't have mkdir)
obsidian create path="Drafts/README.md" content="<contents of Drafts-README.md>" overwrite
obsidian create path="AI Notes/README.md" content="<contents of AI-Notes-README.md>" overwrite
obsidian create path="AI Notes/Ideas/Coding/.keep" content="" overwrite
obsidian create path="AI Notes/Ideas/Book/.keep" content="" overwrite
obsidian create path="AI Notes/Ideas/Trip/.keep" content="" overwrite
obsidian create path="AI Notes/Daily/.keep" content="" overwrite
obsidian create path="AI Notes/Knowledge/.keep" content="" overwrite
obsidian create path="AI Notes/Projects/.keep" content="" overwrite
obsidian create path="Secure Vault/README.md" content="<contents of Secure-Vault-README.md>" overwrite
```

### Shell fallback:
```bash
VAULT="/path/to/vault"
mkdir -p "$VAULT/Drafts"
mkdir -p "$VAULT/AI Notes/Ideas/Coding"
mkdir -p "$VAULT/AI Notes/Ideas/Book"
mkdir -p "$VAULT/AI Notes/Ideas/Trip"
mkdir -p "$VAULT/AI Notes/Daily"
mkdir -p "$VAULT/AI Notes/Knowledge"
mkdir -p "$VAULT/AI Notes/Projects"
mkdir -p "$VAULT/Secure Vault"

# Copy READMEs (from skill's assets/folder-readmes/)
cp "<skill-path>/assets/folder-readmes/Drafts-README.md" "$VAULT/Drafts/README.md"
cp "<skill-path>/assets/folder-readmes/AI-Notes-README.md" "$VAULT/AI Notes/README.md"
cp "<skill-path>/assets/folder-readmes/Secure-Vault-README.md" "$VAULT/Secure Vault/README.md"
echo "✅ Vault structure created."
```

---

## Step 4 — Migrate existing notes (optional)

After backup, offer to scan existing notes and suggest where they belong:

> "Would you like me to scan your backed-up notes and suggest which ones should go into `Drafts/` vs `AI Notes/`? I can help migrate them, or you can do it manually."

**If user says yes:**

For each note in the backup:
1. Read its content with `obsidian read path="..."` or `cat`
2. Determine if it's a draft (raw, personal) or already refined (structured)
3. Suggest:
   - Raw/messy → move to `Drafts/` and offer to refine
   - Already structured → move to appropriate `AI Notes/` subfolder
   - Clearly private → suggest moving to `Secure Vault/` (the user must do this themselves)

**Migration command:**
```bash
# Obsidian CLI (updates internal links automatically)
obsidian move path="_backup_YYYYMMDD/my-note.md" to="Drafts/"

# Shell
mv "/path/to/vault/_backup_YYYYMMDD/my-note.md" "/path/to/vault/Drafts/"
```

**Never move anything to `Secure Vault/` automatically.** If a note seems private, tell the user and let them decide.

---

## Step 5 — Verify the structure

After setup, confirm everything is in place:

```bash
# Obsidian CLI
obsidian folders
obsidian files folder="Drafts"
obsidian files folder="AI Notes"

# Shell
find "/path/to/vault" -maxdepth 2 -type d | sort
```

Show the user a summary:
```
✅ Vault initialized!

📁 Drafts/          — ready for your raw notes
📁 AI Notes/        — ready for refined, graph-linked notes
  └── Ideas/Coding/
  └── Ideas/Book/
  └── Ideas/Trip/
  └── Daily/
  └── Knowledge/
  └── Projects/
🔒 Secure Vault/    — AI-free zone

Backed up X existing notes to: _backup_YYYYMMDD_HHMMSS/
```

---

## Enabling Obsidian CLI

Remind the user how to enable Obsidian CLI if not already done:

> **To use Obsidian CLI commands:**
> 1. Open Obsidian
> 2. Go to **Settings → General**
> 3. Enable **Command line interface**
> 4. Follow the prompt to register Obsidian CLI
> 5. Obsidian must be running for CLI commands to work
>
> Then use: `obsidian help` to confirm it's working.
