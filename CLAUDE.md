# RcVCite

@HANDOFF.md

## Handoff protocol

This project owns its handoff state. `HANDOFF.md` in this directory is the only
"where we left off" file that applies here — never read, merge, or carry over a
`HANDOFF.md` belonging to another project, and never write this project's state
into one.

**At session start:** `HANDOFF.md` above is auto-read. Treat it as the starting
context and pick up from its "Next steps".

**At session end** — when `/handoff` is run, or the user says they're wrapping
up / signing off / done for now — rewrite `HANDOFF.md` from scratch:

1. Overwrite the whole file; do not append to it. Stale entries are the failure
   mode this file exists to prevent.
2. Keep the section headings: Project, Where we left off, Current state,
   Next steps, Notes / gotchas.
3. Record the live facts — current branch, whether the tree is clean, whether
   tests were run and what they said. State failures plainly.
4. Write "Next steps" so a fresh session on another machine can act on it
   without asking what was meant.
5. Keep the "Project" section current if the layout or build commands change.

`HANDOFF.md` syncs between machines via Google Drive, so it is the handoff —
don't rely on conversation scrollback surviving the move.

## Build and test

    make          # extensions + website
    make test     # npm run test -> node tests/test.js
    make clean

CircleCI runs the `extensions`, `tests`, and `website` jobs. `make circleci-local`
reproduces them, but it fails fast if the working tree has uncommitted changes.

## Project notes

The API this project was built against has been turned off. The sources are
published for archival so developers can retarget them at other APIs — assume
anything touching the remote API is non-functional until ported.
