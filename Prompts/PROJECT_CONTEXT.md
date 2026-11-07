---
schema_version: 1
record_type: project-context
last_updated: "2026-11-07T22:35:00+11:00"
updated_by: claude-code
---

# Project Context

## Quick start

Read `DECISIONS.md`, `KNOWLEDGE.md`, and `WORK_LOG.md`, then inspect Git status and any active
task tracker before substantive work.

## Objective

Analyse SolarEdge DC power-optimiser data. The specific research question, outputs and definition
of success have not been recorded yet; capture them in `Problem statement/` when they are set.

## Current status

- Baseline commit: `fe3ed37` (on `origin/main`).
- Working tree: dirty at 2026-11-07T22:35+11:00. Uncommitted, owned by claude-code (bootstrap
  session): `Prompts/WORK_LOG.md`, `Prompts/KNOWLEDGE.md`, `Prompts/PROJECT_CONTEXT.md` and the
  new transcript under `Prompts/Chat history/`.
- Summary: Bootstrapped on 2026-11-07 (commit `f684256`) with an empty object-oriented package
  `dc_optimiser_data/`, a `.venv` on Python 3.13 and this project log. The human then added the
  upstream SolarEdge dataset at `dc_optimiser_data/Data/` (commit `fe3ed37`; KNOW-20261107-02).
  No analysis code yet.

## Active work

| Agent | Status | Task | Branch | Files in scope | Tracker | Updated |
|---|---|---|---|---|---|---|
| — | — | No active work registered | — | — | — | — |

## Blockers

- None registered.

## Next actions

1. human: write the first problem statement (question, outputs) in `Problem statement/`.
2. human: decide whether the dataset stays at `dc_optimiser_data/Data/` (tracked, inside the
   package) or moves to `data/raw/` (gitignored by CCDS). Loader classes should take the path as
   a constructor argument either way.
3. Next agent: register the first substantive task here before editing.

## Authoritative references

- `Rules/Coding conventions.md` — object-oriented package and notebook rules.
- `Rules/README.md` — index of project-wide rules.
- `../24_09_24_Solar_Edge/CLAUDE.md` — origin of the dataset; reconstruction method and `.PAN`
  keys.
- `Long-term task tracker/_template/` — copy per multi-session task.

## Latest handoff

2026-11-07, claude-code: bootstrap complete and pushed; dataset added by the human and recorded;
next step is the problem statement.
