# 📝 Drafts

This is your **raw thinking space** — write anything here, exactly as it comes to mind.

## What goes here
- Rough ideas you just had
- Braindumps before you've organized your thoughts
- Voice-to-text transcripts, messy meeting notes
- Half-formed plans, fragments, one-liners with potential
- Any note that isn't ready to be structured yet

## How it works
1. You write freely — no structure needed, no formatting required
2. When you're ready, ask the AI assistant to process a note
3. The AI reads your draft and generates a clean refined note in the `AI Notes/` folder
4. A small **sync header** is added to the top of your draft to link it to its refined version
5. Your original content is **never modified** — only the header at the top changes

## The sync header
When a draft has been processed, you'll see this at the top:
```
---
status: refined
refined_id: RID-YYYYMMDD-XXXX
ai_note: "[[AI Notes/...]]"
last_synced: YYYY-MM-DD
---
```
This links your draft to its AI-refined counterpart. Don't delete the `refined_id` — it's how the AI tracks which notes belong together.

## Tips
- Don't self-censor here — messy is fine
- You can update a draft after it's been refined; just ask the AI to sync again
- If a note feels too personal or sensitive, move it to `Secure Vault/` instead
