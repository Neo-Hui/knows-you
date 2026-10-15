# Behavioral and psychological hypotheses

This is the optional module that makes the profile more than a list of preferences.
It is also the part most likely to go wrong, so it has stricter rules than everything else.

## The default: record proactively

Do not ask the user for permission before writing a hypothesis, and do not wait to be
reminded. A profile that needs a signature on every line never accumulates anything,
and the user's whole reason for having this setup is that it should get to know them
over time.

Proactive does **not** mean unconstrained. Four requirements apply to every entry.

## The four requirements

| Requirement | Meaning |
| --- | --- |
| **Evidence** | At least two independent observations. One remark is not a pattern. |
| **Confidence** | `tentative` / `probable` / `confirmed`. Reserve `confirmed` for what the user stated about themselves. |
| **Alternative** | At least one other plausible explanation. Without this the entry stops being falsifiable. |
| **Review date** | A date to re-read it. On that date, revise or retire it — do not quietly keep it. |

## Why the alternative explanation is mandatory

The failure mode of a quiet user model is not offence, it is **self-reinforcement**:
the more the agent explains the user through its own hypotheses, the more confirmed
those hypotheses feel, and the user ends up with a stubborn impression rather than an
assistant that understands them. The alternative column is the brake.

## Hard limits

- **Never** a diagnosis, a personality-disorder label, or a claim about a protected
  characteristic.
- **Never** claims about health, relationships, finances, or hidden beliefs.
- **Never** treat a hypothesis as fact when answering, deciding, or advising.
- **The user's own explanation always wins** and replaces the inference. Record the
  correction in `## History` so the same guess is not made twice.

## Scope: this is for the owner of the vault

The module assumes the person being described is the person who installed it and
authorized it. Do not use it to build models of third parties — colleagues, family,
clients, or users — from other people's messages, files, or data. That is a different
thing entirely, and not what this project is for.

## Format

Keep entries in `preferences/pref-psychological-hypotheses.md`, and only a one-line
index in `preferences/user-profile.md` (the profile is read on every task and must stay
short).

```markdown
### H1 · <short name>

- Hypothesis: <one or two sentences>
- Confidence: tentative | probable | confirmed
- Evidence: <specific, non-sensitive observations>
- Alternatives: <at least one other plausible explanation>
- Review: YYYY-MM-DD
```

Example, with a made-up person:

```markdown
### H1 · 代价一旦被量化就迅速决断

- Hypothesis: 面对陌生事物时先确认"这是什么、代价多大"，一旦代价被量化且可逆，就果断决定。
- Confidence: probable
- Evidence: 装某个工具前先问"这是什么、必须装吗"，听到体积和卸载方式后立刻同意；对另一个服务只问了一句"那就上吧"。
- Alternatives: 可能只是对陌生工具谨慎，熟悉领域并不这样；也可能真正的变量是"能否干净卸载"而不是体积。
- Review: 2026-11-15
```

## Surfacing the picture

Occasionally — not every session — show the user a short readout of the current
sketch ("this is what I currently think about how you work"). Drift is caught by the
user seeing the picture and disagreeing with it, so make that easy to do.
