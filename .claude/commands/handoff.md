---
description: Checkpoint this project — rewrite HANDOFF.md fresh
allowed-tools: Bash(git status:*), Bash(git branch:*), Bash(git log:*), Bash(git diff:*), Bash(git rev-parse:*), Read, Write, Edit
---

Checkpoint **this project only** (`RcVCite`). Ignore any handoff state from
other projects; write only to `HANDOFF.md` in this repository.

Gather the live state first:

- Current branch: !`git rev-parse --abbrev-ref HEAD`
- Working tree: !`git status --short`
- Recent commits: !`git log --oneline -5`

Then overwrite `HANDOFF.md` completely — do not append, do not preserve stale
lines from the previous checkpoint. Keep these headings:

- **Project** — what RcVCite is, the directory layout, build and test commands.
  Update it only if something actually changed.
- **Where we left off** — what was done this session, in a few concrete sentences.
- **Current state** — branch, whether the tree is clean or what's outstanding,
  whether tests were run and their result. Report failures as failures.
- **Next steps** — the specific next actions, written so a session on another
  machine can start work without asking for clarification.
- **Notes / gotchas** — anything that would cost the next session time to
  rediscover.

$ARGUMENTS

After writing, show the user a two-or-three line summary of what was checkpointed.
Do not commit or push unless asked.
