# Project-local skills

Repeatable, slash-invocable skills specific to THIS project and unlikely to be useful elsewhere.
Claude Code auto-discovers any `.claude/skills/<name>/SKILL.md` here and exposes it as `/<name>`.
(For skills you want in *every* project, use your personal `~/.claude/skills/` instead.)

## Create a new project skill
1. Copy the starter template into a new folder named after the command you want:
   `.claude/skills/<your-skill-name>/SKILL.md`
   The folder name becomes the slash command — e.g. `monthly-export/` -> `/monthly-export`.
2. Edit the `description:` line so Claude knows WHEN to use it, then write the steps.
3. It is invokable immediately — no restart needed.

## Notes
- `README.md` and `_NEW_SKILL_TEMPLATE.md` are loose files (not inside a `<name>/SKILL.md`
  folder), so they are NOT discovered as skills and never appear in the slash menu.
- Commit `.claude/skills/` to git so these skills travel with the project.
