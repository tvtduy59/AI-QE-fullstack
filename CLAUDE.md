@AGENTS.md

## Claude Code conventions

- Canonical skills live in `.agents/skills/`.
- `.claude/skills/` contains links to those skills.
- Edit canonical files rather than creating separate Claude copies.
- Interpret `$skill-name` references in shared instructions as references
  to the same skill; explicit Claude invocation uses `/skill-name`.
- Use the shared repository knowledge and test-plan files.
- Preserve read-only remind-me behavior.
- Never execute tests before the required human review and run authorization.