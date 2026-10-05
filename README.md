# backlog

A Claude Code skill that keeps your ideas and to-dos in one plain file, `BACKLOG.md`. Capture an idea in a few seconds, then carry on. Claude can read the file in any session, so it always knows what is on your list.

## Why this skill

It is simple. One file, one command, nothing to configure.

It never works on your ideas. It only captures and ranks them, quick wins first.

### How to use

Use /backlog
or simply just tell Claude to backlog for you.

Subcommands: `add <idea>`, `list`, `prioritize`, `done <id>`, `drop <id>`, `edit <id> <field>=<value>`. 

### Reminders (optional)
Claude can remind you. Add this line to your `CLAUDE.md`, and Claude checks your list when a session starts:

    At the start of a session, read BACKLOG.md and mention anything urgent.

I kept the accuracy point. The skill doesn't remind you on its own. The CLAUDE.md line does that, and the README now says so in one sentence.

## Install

Run this in a terminal:

```
npx skills add ellebelle99/backlog-skill
```

Add `--global` to install it for every project. Then run `/backlog`.

Without Node: copy `skills/backlog/` into your project's `.claude/skills/` (or `~/.claude/skills/` for every project).

If `BACKLOG.md` does not exist, the skill creates it from its template.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). An example of the file the skill produces is in [examples/BACKLOG.md](examples/BACKLOG.md).

## License

MIT, see [LICENSE](LICENSE).
