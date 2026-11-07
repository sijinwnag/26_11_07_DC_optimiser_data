---
schema_version: 1
record_type: knowledge
last_updated: "2026-11-07T22:35:00+11:00"
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

### KNOW-20261107-02 — `dc_optimiser_data/Data/` is a copy of upstream Solar_Edge `Data/`

- Status: `verified`
- Scope: Input dataset.
- Fact: `dc_optimiser_data/Data/` holds 21 SolarEdge sites (folders named by site ID, 3455043 to
  4197100) plus five site-summary workbooks (`2025 - New Sites Overview*.xlsx`,
  `25_05_01_Newsites_summary.xlsx`, `25_06_24_Newsites_summary_fordotpoint*.xlsx`). Each site
  folder has `<site> - <module>.PAN`, `inverter_metadata.csv`, `optimizer_metadata.csv` and
  `march/ june/ september/ december/` subfolders with `optimizer_data.csv`, `inverter_data.csv`
  and `site_daily_data.csv` (site 4197100 has no `march/`). `optimizer_data.csv` columns:
  timestamp index, `site_id`, `reporter_id`, `power`, `delta_time`, `energy_since_last_telem`,
  `panel_voltage`, `temperature`, `panel_current`, `panel_temperature`; the June files start
  2024-06-15. The top-level listing matches `../24_09_24_Solar_Edge/Data/` exactly.
- Basis: listing compared in full; contents checked by sha256 on three files only
  (`3455043/june/optimizer_data.csv`, `4197100/optimizer_metadata.csv`,
  `25_05_01_Newsites_summary.xlsx`), all identical. Other files are assumed, not proven, identical.
- Implication: The data is git-tracked inside the package folder, not in CCDS's gitignored
  `data/raw/`; it is already pushed, so it is in GitHub history for good. Treat it as read-only
  input. Upstream's `CLAUDE.md` documents its method and the `.PAN` keys.
- Source: commit `fe3ed37`; `../24_09_24_Solar_Edge/Data/`.
- Last verified: `2026-11-07T22:35:00+11:00`
- Superseded by: `none`
