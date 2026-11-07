# GEMINI.md

Guidance for Gemini CLI working in this repository: `26_11_07_DC_optimiser_data`, an analysis of
SolarEdge DC power-optimiser data. The package is `dc_optimiser_data/` (Python 3.13, `.venv` at the
repository root; call `.venv/Scripts/python.exe` and `.venv/Scripts/ruff.exe` explicitly).

## Code conventions

**Object-oriented by default.** Reusable logic is a class in `dc_optimiser_data/` (one class per file,
re-exported from `__init__.py`); notebooks only instantiate classes and call their methods — no
`def` / `class` in notebook cells. Full rules: `Rules/Coding conventions.md`.

<!-- BEGIN MULTI-AGENT PROJECT LOG -->
## Multi-Agent Project Memory

This repository uses vendor-neutral, Git-tracked memory under `Prompts/`. Before substantive work,
read `Prompts/PROJECT_CONTEXT.md`, `Prompts/DECISIONS.md`, `Prompts/KNOWLEDGE.md`, and
`Prompts/WORK_LOG.md`; then inspect Git status and any active task tracker.

Use this authority order: current user instructions; `Rules/` and authoritative domain documents;
accepted decisions; current project context; verified knowledge; then work logs, Git history, and
transcripts as supporting evidence.

Register substantive work in `PROJECT_CONTEXT.md` with agent, status, task, branch, intended files,
tracker, and timestamp. Do not edit files claimed by another active agent without an explicit
handoff. Treat unowned existing changes as protected.

After meaningful implementation, investigation, failure, decision, or handoff, update current state
and append one attributed entry to `WORK_LOG.md`. Add durable choices to `DECISIONS.md` and sourced
reusable facts to `KNOWLEDGE.md`. Never silently rewrite another agent's entry; supersede or correct
it with evidence. Keep summaries concise, preserve provenance, and never store secrets.

Full transcripts are historical evidence, not startup reading. The closing step of a logged session
archives its transcript under `Prompts/*chat_hist*/` and links it from the work entry; always write
the concise work entry as well, and search the archive selectively. Detailed execution for a
long-running task stays in its task tracker, linked from the project context.
<!-- END MULTI-AGENT PROJECT LOG -->
