---
name: keepass
description: Safely retrieve or maintain credentials and account metadata in a KeePass-compatible database when a task requires secret-backed access or password-vault work.
---

# KeePass

Requires a KeePass-compatible CLI or approved application.

Obtain the database location and entry mappings from Context. Prefer a compatible command-line client available on `PATH`; use GUI automation only when explicitly requested.

## Secret handling

- Never read a KeePass database as a normal file.
- Supply the database password through secure input or an environment variable, never as a command-line argument.
- Retrieve only the entry and attributes required for the current task. Do not enumerate the vault without a reason.
- Do not print, log, persist, or place secrets in shell history, Markdown, temporary files, or version control.
- When a downstream command needs a credential, pass it without displaying it and clear temporary environment variables afterward.
- Display or copy a secret only when the user explicitly requests that specific disclosure.

## Changes

Creating, editing, moving, or deleting vault entries requires explicit instruction. Resolve ambiguous entry names before acting, preserve existing attributes unless asked to change them, and verify writes by reading back the intended fields without displaying secret values.

If no safe supported client is available, stop and explain what capability is missing rather than improvising direct database access.
