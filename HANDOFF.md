# HANDOFF — RcVCite

> Session continuity for **this project only**. Rewritten fresh by `/handoff`.
> Scope: the RcVCite repository. Do not pull state from other projects.

## Project

RcVCite — a scripture reference citation/linking tool, published for archival.
The upstream API the project depended on was shut down, so the sources are
public for developers who want to retarget it at another API.

Layout:
- `core/` — `RcVCite.js`, `versification.js`, stylesheets. The actual library.
- `extensions/` — browser bookmarklet + WordPress plugin packaging (`make -C extensions`).
- `website/` — PHP site sources (`make -C website`).
- `tests/` — `npm test` runs `tests/test.js` (jsdom-based).
- `experimental/versification_generator` — generator scratch work.

Build: `make` (extensions + website), `make test`, `make clean`.
CI: CircleCI, jobs `extensions`, `tests`, `website`; `make circleci-local` runs them locally.

## Where we left off

Installed the handoff kit into this project so RcVCite carries its own handoff
state instead of inheriting another project's. No source code was touched.

## Current state

- Branch: `claude/folder-scope-constraint-pw6505`
- Working tree: handoff kit files added; no changes under `core/`, `extensions/`,
  `website/`, `tests/`, or `experimental/`.
- Tests: not run this session.

## Next steps

- Nothing pending. Start the next session by stating the goal for RcVCite.

## Notes / gotchas

- The original API is dead — any functional work means porting to a different
  scripture API, not fixing the existing calls.
- `make circleci-local` refuses to run with an uncommitted working tree.
- `.claude/last-session.md` is a per-machine breadcrumb and is gitignored;
  `HANDOFF.md` is the file that actually travels between machines.
