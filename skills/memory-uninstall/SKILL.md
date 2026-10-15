---
name: memory-uninstall
description: Remove the memory skills, and only if the user explicitly asks, delete the saved memory too. Use when the user asks to uninstall, remove, or delete this memory setup.
---

Explicit user instructions override everything here.

## Two different requests

**Removing the skill** and **deleting the notes** are not the same thing, and the user
usually means the first.

### 1. Remove the skill (memory preserved)

Triggered by: "uninstall this", "remove the memory skill", `卸载`, `别用它了`.

Delete the installed skill folders (`memory-recall`, `memory-save`, `memory-maintain`,
`memory-uninstall`) from the agent's skills directory, and remove any AGENTS.md /
config block that pointed at them.

**Leave the vault folder untouched.** The notes are the user's own files, written in
plain Markdown, and they stay readable in any editor after the skill is gone.

### 2. Delete the memory as well (purge)

Only when the request explicitly says so: "delete everything you remember",
`把记忆一起删掉`, `清空记忆`, `purge`.

Only then remove the vault folder. Before deleting:

- Show what is about to be deleted (folder path, note count, first lines of `INDEX.md`).
- Say clearly that this is irreversible and not recoverable from the skill.

If the request is ambiguous, do the non-destructive one and say what you did.

## Verify and report

After either action, state plainly:

1. which folders were removed,
2. whether the vault still exists (and where),
3. if purged, that it is gone.

Never report a deletion you did not verify.
