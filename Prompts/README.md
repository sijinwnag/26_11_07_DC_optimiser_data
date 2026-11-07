# Prompts

Working area for AI-assisted development and shared project memory.

- `PROJECT_CONTEXT.md` — bounded current state, ownership, blockers, and next actions.
- `DECISIONS.md` — append-only durable choices, rationale, consequences, and evidence.
- `KNOWLEDGE.md` — sourced facts and invariants that future work should not rediscover.
- `WORK_LOG.md` — concise chronological session summaries and cross-agent handoffs.
- `Problem statement/` — dated problem statements and approved project briefs.
- `Chat history/` — full `/export` transcripts filed at the end of each logged session and
  linked from `WORK_LOG.md` `Transcript:` fields; historical evidence, search selectively.
- `Project docs/` — maintained explanations of project methods and architecture.
- `Long-term task tracker/` — detailed state for work spanning multiple sessions; copy
  `_template/` per task and link active trackers from `PROJECT_CONTEXT.md` instead of duplicating
  their execution detail.

Before substantive work, read the four canonical records and inspect Git status. Register active
ownership before editing, preserve unowned changes, and add an attributed work entry after meaningful
work or a handoff. Git records what changed; project memory records context, rationale, evidence, and
what should happen next.
