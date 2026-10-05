# Release notes

## v1.1.0 (05-10-2026)

- `/backlog` and `/backlog this` now propose items from the conversation as a bullet list. Reply "all" or name the ones you want.
- `/backlog this` proposes only the subject of your last message.
- `/backlog list` shows the list. It was the default for a bare `/backlog` before.
- New backlog files include a default Areas line.
- README restructured, example file and contributing guide tightened.

## v1.0.0 (05-10-2026)

First public release.

- Subcommands: `add`, `list`, `prioritize`, `done`, `drop`, `edit`
- Creates `BACKLOG.md` from a built-in template when it does not exist
- Open items sorted by value, then effort, so quick wins rise to the top
- Never executes backlog items
- Install with `npx skills add ellebelle99/backlog-skill`
