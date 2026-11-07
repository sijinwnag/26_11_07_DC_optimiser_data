---
schema_version: 1
record_type: work-log
last_updated: "2026-11-07T22:35:00+11:00"
updated_by: claude-code
---

# Work Log

Append concise, chronological session records. Git remains authoritative for file changes.

## Entry template

### WORK-YYYYMMDD-HHMM-agent — Task title

- Timestamp: `YYYY-MM-DDTHH:MM:SS+HH:MM`
- Agent: `human | codex | claude-code | gemini-cli`
- Task: Short task name.
- Outcome: `complete | partial | blocked | handed-off`
- Request: The user goal or reason for the work.
- Actions: Concise summary of investigation or implementation.
- Files: Paths changed or inspected materially.
- Validation: Checks run and their results.
- Decisions: Related decision IDs or `none`.
- Knowledge: Related knowledge IDs or `none`.
- Tracker: Link or `none`.
- Transcript: Link or `not archived`.
- Commit: Commit hash or `uncommitted`.
- Next action: What remains and who owns it.

## Entries

## WORK-20261107-2145-claude-code — Bootstrap project

- Timestamp: `2026-11-07T21:45:00+11:00`
- Agent: `claude-code`
- Task: Bootstrap the DC optimiser data project.
- Outcome: `complete`
- Request: `/setup-new-project` with name "DC optimiser data". The user chose the dated name
  `26_11_07_DC_optimiser_data` over the undated `DC-optimiser-data`, and chose to copy the
  package list from `26_05_19_SE_validation/requirements.txt` (declined adding `ipykernel` and
  the leaner data stack).
- Actions: Scaffolded with Cookiecutter Data Science (ruff, no tests, no docs, no code scaffold);
  added `Rules/`, `Prompts/` task folders and this four-record log, the AGENTS/CLAUDE/GEMINI
  adapters and `.claude/skills/`; wrote requirements; created `.venv` and installed; created the
  private GitHub repo and pushed the initial commit.
- Files: whole repository (initial commit).
- Validation: `check_log_system.py` run after setup; `pip install -r requirements.txt` exit 0;
  `import dc_optimiser_data` from the venv.
- Notes: The log checker only counts `## DEC-…` / `## WORK-…` headings (its regex), although the
  skill's own entry templates use `###`; the first draft used `###` and the checker silently
  reported 0 entries until the headings were promoted. The CCDS-generated `Makefile`, `README.md`
  and `pyproject.toml` fail `git diff --check` (trailing spaces); left as generated. The transcript
  was saved later in the session with session-transcript-exporter (the desktop app has no
  `/export`).
- Decisions: DEC-20261107-01
- Knowledge: KNOW-20261107-01
- Tracker: none
- Transcript: [2026-11-07-213900-dc-optimiser-data-project-setup.txt](<Chat history/2026-11-07-213900-dc-optimiser-data-project-setup.txt>)
- Commit: `f684256`
- Next action: human to write the first problem statement.

## WORK-20261107-2157-human — Add SolarEdge site data (backfilled)

- Timestamp: `2026-11-07T21:57:09+11:00`
- Agent: `human`
- Task: Copy the upstream SolarEdge site dataset into the project.
- Outcome: `complete`
- Request: Backfilled by claude-code at 2026-11-07T22:35+11:00 from commit `fe3ed37` (message
  "d"); the human's intent is not recorded beyond the commit.
- Actions: Added `dc_optimiser_data/Data/` (317 files, about 317 MB on disk) and pushed it to
  `origin/main`. See KNOW-20261107-02 for contents and provenance.
- Files: `dc_optimiser_data/Data/**`
- Validation: claude-code compared three files by sha256 with
  `../24_09_24_Solar_Edge/Data/`; all three match.
- Decisions: none
- Knowledge: KNOW-20261107-02
- Tracker: none
- Transcript: not archived
- Commit: `fe3ed37`
- Next action: human to confirm whether the data should stay inside the package folder (see
  PROJECT_CONTEXT next actions).
