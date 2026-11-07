---
schema_version: 1
record_type: decisions
last_updated: "2026-11-07T21:45:00+11:00"
updated_by: claude-code
---

# Decision Log

Decisions are append-only. Supersede an earlier decision with a new entry and cross-link both IDs.

## Entry template

### DEC-YYYYMMDD-NN — Decision title

- Date: `YYYY-MM-DDTHH:MM:SS+HH:MM`
- Status: `proposed | accepted | rejected | superseded`
- Author: `human | codex | claude-code | gemini-cli`
- Context: Why a choice was required.
- Decision: The selected behavior or constraint.
- Rationale: Why this option was selected.
- Consequences: What future contributors and agents must do differently.
- Evidence: Link to the user instruction, maintained document, tracker, code, or transcript.
- Supersedes: `none` or another decision ID.

## Decisions

## DEC-20261107-01 — Object-oriented package; notebooks only call classes

- Date: `2026-11-07T21:45:00+11:00`
- Status: `accepted`
- Author: `human`
- Context: Projects bootstrapped without a coding rule accumulated loose notebook functions that
  later had to be refactored into classes.
- Decision: Reusable logic lives in classes in `dc_optimiser_data/` (one class per file,
  re-exported from `__init__.py`); notebooks import in the first cell and contain no `def` or
  `class`.
- Rationale: Starting object-oriented is cheaper than retrofitting it.
- Consequences: Every agent writes or updates a class first, then calls it from notebooks or a
  `python -m dc_optimiser_data.<module>` CLI.
- Evidence: [Rules/Coding conventions.md](../Rules/Coding%20conventions.md); fixed convention of
  the user's `setup-new-project` skill.
- Supersedes: `none`
