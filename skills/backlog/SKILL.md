---
name: backlog
description: Capture, list, and prioritise ideas in BACKLOG.md — never executes items
allowed-tools: Read, Edit, Write
argument-hint: "[this | add <idea> | list | prioritize | done <id> | drop <id>]"
---

# /backlog

Manage a single repo-root `BACKLOG.md` of ideas/tasks: **capture, list, prioritize, and update**.

> **This skill strictly MANAGES the backlog — it NEVER executes the items.** Its purpose is to capture ideas cheaply (defer instead of doing) and keep them prioritised. 
Capturing must be fast and low-token.

**Backlog file:** `BACKLOG.md` at the **repository root** (one backlog only — never create per-folder backlogs). 

Create it from the template below if it's missing.

## Subcommands (parse from `$ARGUMENTS`)

- **(no args)** or **this** → **propose** items from the conversation (see Propose). This is the default.
- **add `<idea>`** → quick-capture a new item (see Capture).
- **list `[open|done|dropped|<area>]`** → show items, optionally filtered by status or area, sorted (see Sorting).
- **prioritize** (alias **groom**) → re-rank; surface "quick wins" (High value + Small effort at the top); flag stale or duplicate items for the user.
- **done `<id>`** → set status = done (move to Closed).
- **drop `<id>`** → set status = dropped (move to Closed).
- **edit `<id>` `<field>=<value>`** → change one field (title / value / effort / area / status).

If `$ARGUMENTS` is freeform text that isn't one of the above subcommands, treat the whole thing as **add**.

## Item schema (minimal + area)

| Field | Values |
|---|---|
| ID | next integer |
| Title | one concise line |
| Value | H / M / L |
| Effort | S / M / L |
| Status | open / done / dropped |
| Area | project-defined tags (e.g. `writing` / `research` / `claude-code` / `repo-meta` / `other`) — set the list once in `BACKLOG.md`'s header and reuse it |

## Propose (`/backlog` or `/backlog this`)

1. Pick the candidates from the conversation so far.
   - `/backlog` alone: every idea, to-do or deferred item the user mentioned.
   - `/backlog this`: the one subject of the user's last message before the command. That is a single candidate.
2. Reply with a bullet list, one line per candidate, then one question: `Add all, or which?`
3. Wait for the answer. Write nothing to `BACKLOG.md` before it.
4. Capture each confirmed item (see Capture) and confirm in one line per item.
5. If the conversation holds nothing to backlog, say so in one line and stop.

## Capture (quick, cheap, no execution)

1. Append the item with **defaults**: Value=`M`, Effort=`M`, Status=`open`, Area inferred from context (else `other`).
2. **Do NOT ask clarifying questions** unless the idea is too vague to even title. **Do NOT start working the item.**
3. Confirm in **one terse line**, e.g. `Added #7: <title> — M/M · research`.

## Sorting

Open items sorted by **Value (H > M > L), then Effort (S < M < L)** — so High-value / Small-effort **quick wins** rise to the top. Closed items (done/dropped) sit in a separate section below.

## File template

```markdown
# Backlog
Managed by `/backlog`. Open items sorted by value (H>M>L) then effort (S<M<L); quick wins (High value · Small effort) at the top.

**Areas:** `admin` · `money` · `home` · `work` · `other`

## Open
| ID | Title | Value | Effort | Area |
|---|---|---|---|---|

## Closed
| ID | Title | Status | Area |
|---|---|---|---|

## Details (optional — only for items needing more than a title)
```

## Rules

- One backlog only: repo-root `BACKLOG.md`. Never split into per-folder backlogs.
- **Never execute or start a backlog item from this skill** — capture / list / prioritise / update only.
- Keep the confirmation terse and edits minimal — this skill exists partly to **save Claude usage**.
- Use the `## Details` section only when an item genuinely needs more than its title; quick-capture never writes details.
- IDs are never reused; keep them stable across status changes.