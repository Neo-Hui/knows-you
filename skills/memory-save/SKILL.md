---
name: memory-save
description: Save durable cross-session information to the external Obsidian memory vault when the user asks to remember, or when a task produces a stable preference, decision, reusable lesson, project fact, or open loop worth preserving.
---

Use explicit user instructions over these rules.

Memory root:
`{{VAULT}}`

Resolve that path from `vault-path.txt` beside this skill. If the file is missing, ask the user for their vault folder and create it.

## Save workflow

1. Before writing, read `preferences/user-profile.md` and search `INDEX.md` plus the target category for an existing note covering the same fact.
2. Prefer updating an existing active note over creating a duplicate. Preserve useful history in `## History` rather than rewriting the reason away.
3. For stable communication preferences, work style, recurring tool choices, interests relevant to work, and personal-assistant expectations, update `preferences/user-profile.md` first. Create a separate preference note only when the rationale or exceptions need more detail.
4. The user has explicitly authorized psychological and behavioral hypotheses when they help the assistant understand recurring motivations, decision patterns, attention, stress responses, communication habits, or blind spots. Record them proactively — see `references/psychological-hypotheses.md` for the four mandatory fields and the hard limits.
5. Store only durable, reusable information:
   - stable user preferences and working style;
   - project constraints, terminology, and architecture context;
   - decisions with their rationale and consequences;
   - lessons and verified solutions;
   - unresolved cross-session work in `open-loops.md`.
6. Never save passwords, tokens, API keys, private keys, authentication cookies, authentication data, financial credentials, private messages, full transcripts, raw logs, or secrets found in source files. Replace credentials with a note that a credential is required.
7. Mark provenance and confidence. Use `confirmed` only for facts the user explicitly stated or clearly approved. Observations and psychological hypotheses are `probable` or `tentative`.
8. For psychological or behavioral hypotheses, do not wait for permission: write them as you notice a pattern. Each one still needs concise evidence from at least two independent observations, at least one plausible alternative explanation, a confidence level, and a review date. Do not create medical diagnoses, personality disorder labels, claims about protected characteristics, or definitive statements about hidden beliefs. The user's self-description always overrides an inference.
9. Keep profile entries to one or two sentences. Let the latest explicit user input override older preferences, and record the change date.
10. Do not save transient status, routine commands, code snapshots, or information already obvious from the current repository.
11. Use `references/memory-format.md` in this skill directory for filenames, frontmatter, note templates, and index rules.
12. Write the note or profile update first, then update the relevant `INDEX.md`. Keep index entries to one line and include the note's `[[wikilink]]`, scope, and one-sentence summary.
13. Confirm to the user exactly what was saved and where. Do not claim a save before the files are written.

If the requested memory contains secrets or the scope is ambiguous, omit the sensitive portion and ask only when the remaining useful fact cannot be determined safely.
