# backlog

A Claude Code skill that keeps your ideas and to-dos in one plain file, `BACKLOG.md`.

Capture an idea in seconds, then carry on.

Claude can read the file in any session, so it always knows what is on your list.


## Why this skill

It is simple: one file, one command, nothing to configure.

It never works on your ideas. It only captures and ranks them, quick wins first.


## Install

    npx skills add ellebelle99/backlog-skill -g

The `-g` installs it for every project.

Installing this way lets `npx skills update` keep the skill current for you.

No Node? Copy `skills/backlog/` into `.claude/skills/`.
Copied skills are not tracked, so `npx skills update` will not update them.


## Use

    /backlog

Claude lists the things from your conversation that could go on the backlog.

Reply "all", or tell it which ones.

`BACKLOG.md` is created the first time.

Other ways to use it:

    /backlog this
    /backlog add Call the dentist
    /backlog list

Also: `prioritize`, `done <id>`, `drop <id>`, `edit <id> <field>=<value>`.


## Reminders (optional)

The skill does not remind you on its own.

To have Claude check your list when a session starts, add this line to your `CLAUDE.md`:

    At the start of a session, read BACKLOG.md and mention anything urgent.


## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

A sample file is in [examples/BACKLOG.md](examples/BACKLOG.md).


## Optional

If you like the skill, a star is appreciated.

Watching the repo is an easy way to keep an eye on changes.


## License

MIT, see [LICENSE](LICENSE).
