# Workspace Operating Rules

## Scope

`Workspace/` is the active operating surface. Use it as the working directory.
The surrounding Obsidian vault is read-only reference material unless the user explicitly authorizes an exception listed in `ALLOW_WRITE_OUTSIDE_WORKSPACE.md`.

## Startup

1. Read Markdown files in `Context/`. Never open binary files or secret stores during bootstrap.
2. Read `Projects/INDEX.md` if present. Load individual project files only when relevant; for logs, read only the latest entries.
3. Inspect skill names and descriptions under `Skills/*/SKILL.md`. Load a skill fully when the user names it or the task clearly matches it.

For an orientation request such as “where shall we begin?”, summarize the relevant personal constraints, active projects, and most useful next step.

## Context and secrets

- `Context/` holds personal facts, account mappings, preferences, and machine-specific configuration.
- Skills must refer to Context rather than duplicate personal details.
- Secrets belong in the configured secret store or environment variables, never in Markdown, logs, command arguments, or version control.
- Do not display a secret unless the user explicitly asks to see that secret.

## Authorization

- Capability is not authorization. Keep actions within the user’s requested scope.
- Read-only inspection may proceed when it is reasonably implied by the request.
- Sending, publishing, purchasing, deleting, changing remote state, or acting as the user requires explicit instruction.
- An instruction containing the action, target, and final content is authorization for that action; do not request redundant confirmation unless something is ambiguous or unusually risky.
- Never broaden a one-time authorization into an ongoing automation.

## Files and changes

- Write only within `Workspace/` unless the user authorizes a documented exception.
- Preserve unrelated and pre-existing changes.
- Prefer minimal, reversible edits. Do not reorganize, rename, or rewrite human-authored prose without a reason grounded in the request.
- For an exception outside `Workspace/`, identify the exact targets, show an example when useful, and confirm the scope before editing.

## Projects

- Projects live in `Projects/`; `Projects/INDEX.md` is the status source of truth.
- Keep plans, tasks, decisions, references, and logs inside the relevant project.
- Use short priority bands only when helpful, and prefer concrete next actions over long task lists.
- New projects use `Templates/Project/Project.md` and begin with at least one plan item.
- Reconcile any ephemeral task tracking back into the project file.

## Skills

- `Skills/` is the canonical, shared skill library for Claude and Codex.
- Use the portable Agent Skills shape: a concise `SKILL.md` with `name` and `description`, plus supporting files only when they provide clear value.
- Write skills around stable human goals. Prefer a domain name such as `finance` over a provider name such as `plaid` when the workflow can span providers.
- Keep personal facts, account names, local paths, and credentials out of skills; resolve them from Context or the environment at runtime.
- Prefer commands available on `PATH` and agent-neutral instructions. Isolate unavoidable Claude-, Codex-, OS-, or tool-specific behavior.
- Preserve authorization boundaries inside every skill. A skill explains a workflow; it does not grant permission to take external action.
- Use scripts only for repeated or deterministic operations. Validate new or changed skills before relying on them.

## Activity logging

When Workspace files change, append one brief entry to `Activity/YYYY-MM-DD.md` with the time, actor, scope, files touched, and outcome. Do not include secrets or message contents.

## Style

Be clear, calm, practical, and concise. Ask only questions that materially change the result; otherwise make and state reasonable assumptions.
