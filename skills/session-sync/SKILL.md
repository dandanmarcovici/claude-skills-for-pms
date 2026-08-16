---
name: session-sync
description: Scan the current session and update project files (context.md, tasks.md, log.md, or similar) with new information that emerged from the discussion but hasn't been captured yet. Use at the end of a working session, especially in a pm-second-brain-style setup where these files are the source of truth. Do not use mid-session, or when nothing new was actually decided.
---

# Session Sync

Scan this session and update project files with new information that emerged from the discussion.

---

## Step 1 — Identify files to sync

Look at all Read tool calls made during this session.

Collect every file that was read, excluding:
- Anything inside `_system/`
- Anything inside `.claude/`
- Memory files
- CLAUDE.md files
- Any file outside the active project folder(s)

What remains is the sync scope: project files that were touched this session.

If no project files were read → output "Nothing to sync." and stop.

---

## Step 2 — Evaluate each file

For each file in scope, ask:

> Did this session produce new information that belongs in this file and is not already there?

Update only if the answer is clearly yes.

**Do not update if:**
- The information is already captured
- The information belongs in a different file
- You are uncertain whether it fits
- The session only *read* the file without producing anything new related to it

When in doubt → skip.

---

## Step 3 — Apply updates

For each file being updated:

- Edit existing content rather than appending new blocks
- Replace outdated information instead of duplicating it
- Keep the file's existing structure and format
- Never invent information, only use what was explicitly discussed in this session
- Never remove existing content unless it was directly contradicted or resolved this session

---

## Step 4 — Output summary

After all updates are done, output:

**Synced:**
- `path/to/file.md` → one line describing what changed

**Skipped:**
- `path/to/file.md` → one line explaining why (nothing new / already captured / uncertain fit)

If no files were updated: "No updates needed."

Keep the summary short. No explanations beyond one line per file.
