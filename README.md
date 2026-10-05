# backlog

A Claude Code skill that captures, lists and prioritises ideas in a single `BACKLOG.md`. 

It manages the list and never executes the items.

## Install

Copy `skills/backlog/` into your project's `.claude/skills/` (or `~/.claude/skills/` for every project), then run `/backlog`.

Subcommands: `add <idea>`, `list`, `prioritize`, `done <id>`, `drop <id>`, `edit <id> <field>=<value>`. If `BACKLOG.md` does not exist, the skill creates it from its template.
