# Memory format

Memory root:
`{{VAULT}}`

Resolve that path from `vault-path.txt` beside this skill. If the file is missing, ask the user for their vault folder and create it.

## Locations

- `preferences/user-profile.md`: fixed structured profile for stable personal context and assistant preferences.
- `preferences/`: detailed preference notes when rationale or exceptions need their own file.
- `projects/`: project identity, constraints, terminology, and pointers to related notes.
- `decisions/`: choices, rationale, alternatives, and consequences.
- `lessons/`: verified problems, solutions, and reusable cautions.
- `context/current-focus.md`: current long-lived focus, not minute-by-minute status.
- `open-loops.md`: unresolved work that should survive the session.

## Filenames

Use lowercase ASCII kebab-case. Start factual notes with `pref-`, `project-`, `decision-`, or `lesson-`. Use a short topic, not a sentence. Examples:

`preferences/user-profile.md` is the fixed profile filename and must not be replaced with another profile note.

- `preferences/pref-pnpm-projects.md`
- `decisions/decision-local-first-storage.md`
- `lessons/lesson-macos-path-aliases.md`

## Frontmatter

```yaml
---
id: decision-local-first-storage
kind: decision
title: Keep external memory local
status: active
scope: global
created: 2026-10-01
updated: 2026-10-01
tags: [memory, local-first]
source: codex-session
---
```

Use `kind: user-profile | preference | project | decision | lesson | context | open-loop` and `scope: global | project`. For project notes, add `project_id` and `project_path` when known.

For personal-context notes add `source: user-stated | observed | imported` and `confidence: confirmed | probable | tentative`. Only `user-stated` or explicitly approved facts may use `confidence: confirmed`.

## User profile rules

Keep `preferences/user-profile.md` organized into stable sections such as `Communication`, `Working Style`, `Tools & Environment`, `Recurring Interests`, `Assistant Expectations`, `Boundaries`, `Open Questions`, and `History`.

Each profile entry should be one or two sentences and include its provenance when not directly confirmed. Update entries in place and append dated changes to `## History`. The latest explicit user statement wins over older assumptions.

## Psychological and behavioral hypotheses

The user has explicitly authorized psychological and behavioral hypotheses when they improve collaboration. Keep them in `preferences/user-profile.md` or a detailed `pref-*` note using this compact form:

```markdown
### <Hypothesis name>
- Hypothesis: <one or two sentences>
- Confidence: <tentative | probable>
- Evidence: <specific, non-sensitive observations>
- Alternatives: <at least one plausible explanation>
- Review: <YYYY-MM-DD>
```

Do not use diagnostic labels or claim certainty about hidden beliefs, health, relationships, protected characteristics, or motives. User self-correction replaces the hypothesis and is recorded in `## History`.

## Note body

Start with one sentence that states the fact. Add sections only when they add value:

```markdown
## Summary

## Reason

## Applies To

## Examples

## Related

## History
```

Use `[[wikilink]]` references for related notes. Links may omit the `.md` extension.

## Index rules

Each category `INDEX.md` lists active notes in this form:

```markdown
- [[decision-local-first-storage]] - Global - Keep memory local and reviewable.
```

Keep entries short. Do not duplicate the full note body in the index. Remove retired notes from the active index after marking them `status: retired`.

## Dates

Use ISO dates in `YYYY-MM-DD`. Use an ISO timestamp only when time of day matters.
