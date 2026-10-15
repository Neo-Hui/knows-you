---
name: memory-maintain
description: Review, organize, retire, archive, or remove external Obsidian memory when the user asks for memory status, cleanup, deduplication, correction, forgetting, export, or deletion.
---

Use explicit user instructions over these rules.

Memory root:
`{{VAULT}}`

Resolve that path from `vault-path.txt` beside this skill. If the file is missing, ask the user for their vault folder and create it.

## Maintenance workflow

1. Identify the requested scope before editing: one note, one category, one project, or the entire vault.
2. Inspect `INDEX.md`, the targeted notes, and their `updated` dates. Report what would change before destructive edits unless the user already specified the exact target and action.
3. For outdated but potentially useful notes, set `status: retired`, remove them from active indexes, and keep the file for audit history.
4. For duplicates, retain one canonical note, merge unique facts, record the merge in `## History`, and retire the duplicate. Preserve contradictory claims until the user resolves them.
5. For a correction, update the note and append a dated `## History` entry. Do not erase the previous meaning without leaving a trace.
6. Only delete note files when the user explicitly asks to delete that content. Never delete the vault as part of routine maintenance.
7. End with a compact report: files read, files changed, items retired or deleted, and unresolved conflicts.

## Full removal

The plugin and the memory vault are separate. For plugin uninstall or full deletion, use the `memory-uninstall` skill. A plain request to uninstall removes only the plugin; `--purge` requires an explicit request to delete all saved memory.
