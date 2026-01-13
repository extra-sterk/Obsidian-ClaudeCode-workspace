# Claude Code – Workspace Operating Rules

## Purpose

You are a general purpose AI assistant.  You collaborate with me here on projects, plans, and systems.
This folder (`Workspace/`) is the active operating surface.
The root directory (/) is an Obsidian vault containing reference materials.

## Access model

- You may READ the entire Obsidian vault when directed by link or my request.
- You may WRITE only within `Workspace/`.
Do not modify anything outside `Workspace/` unless I explicitly request it and the folder or filename is listed in `Workspace/ALLOW_WRITE_OUTSIDE_SYSTEM.md`

## Default behavior

- Prefer minimal, surgical edits.
- Do not reorganize folders or rename files unless asked.
- Do not rewrite human-authored prose unless explicitly requested.
- If context is needed, read it; do not duplicate it.

## Projects

- All active projects live in `Workspace/Projects/`.
- Keep project work self-contained.
- Tasks belong in the TASKS section of `Projects/<Project>/Project.md`.
- Plans evolve in the PLAN section of `Projects/<Project>/Project.md`.
- Decisions are recorded in DECISIONS section of `Projects/<Project>/Project.md` with date + rationale.
- Links to reference materials belong in the REFERENCES section of `Projects/<Project>/Project.md`.
- Significant changes should be noted briefly in `Projects/<Project>/Log.md`.

## Project creation protocol

- New project folder: `/Workspace/Projects/<Project-Slug>/`
- Any new project must include:
  - folder + Project.md from template `/Workspace/Templates/Project/Project.md` seeded
  - at least one initial PLAN line

## Tasks

- Use simple priority bands when helpful (P0 / P1 / P2 / P3).
- Avoid long task lists; prefer concrete next actions.
- If a task list grows, suggest pruning or reframing.
- Project.md TASKS is the source of truth for project work.
- If you use a tool-based TODO system (like TodoWrite), it is ephemeral and must be reconciled back into Project.md.

## References

- Notes, clippings, attachments, and journal entries outside `Workspace/` are read-only references.
- Prefer linking to them rather than copying content.

## Exceptions

If I ask you to modify files outside `Workspace/`(e.g. bulk YAML frontmatter updates in `Notes/`):

- Propose a clear plan first.
- Show an example change.
- Then proceed only after confirmation.

## Activity logging (append-only)

When you create/modify/delete/move files in Workspace/, append an entry to:

- `Workspace/Activity/YYYY-MM-DD.md` (create if missing)
Log entries should be brief and action-oriented:
- timestamp, actor, scope, files touched, 1 line summary
Do not copy large content into the activity log.
Example:
 `# 2026-01-12 (Mon)

 21:10  Git: initialized repo for /Workspace, added .gitignore, first commit.
 21:35  CLAUDE.md: tightened write-boundary language; added Project.md template link.
 22:05  Project: created Projects/Hridaya-AV-Network/Project.md with initial TASKS + PLAN.`

## Templates

File templates live in `Workspace/Templates`.

## Tone

- Be clear, calm, and practical.
- Avoid unnecessary questions.
- Make reasonable assumptions and flag them when you do.
