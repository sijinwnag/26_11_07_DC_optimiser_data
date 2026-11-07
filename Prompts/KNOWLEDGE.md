---
schema_version: 1
record_type: knowledge
last_updated: "2026-11-07T21:45:00+11:00"
updated_by: claude-code
---

# Knowledge Register

Record sourced facts and invariants that future work would otherwise have to rediscover.

## Entry template

### KNOW-YYYYMMDD-NN — Knowledge title

- Status: `verified | provisional | superseded`
- Scope: The subsystem, dataset, workflow, or domain covered.
- Fact: The concise reusable finding.
- Implication: How this changes future work.
- Source: Link to maintained documentation, code, data, tracker, commit, or transcript.
- Last verified: `YYYY-MM-DDTHH:MM:SS+HH:MM`
- Superseded by: `none` or another knowledge ID.

## Entries

### KNOW-20261107-01 — Use the project `.venv` interpreter explicitly

- Status: `verified`
- Scope: Tooling on this Windows machine.
- Fact: Dependencies and the editable `dc_optimiser_data` install live in `.venv`; call
  `.venv/Scripts/python.exe` and `.venv/Scripts/ruff.exe`. Bare `python` on PATH is the system
  Python 3.13 without the editable install, and `make` is not installed.
- Implication: Do not reinstall or recreate the venv to fix an import; check you are using the venv
  interpreter first.
- Source: [requirements.txt](../requirements.txt) (last line `-e .`); bootstrap session 2026-11-07.
- Last verified: `2026-11-07T21:45:00+11:00`
- Superseded by: `none`
