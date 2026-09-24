# README

## Summary

Workspace intends to provide a space for AI agent(s) to work in the context of an Obsidian vault.

## Usage

Shared instructions live in [Operating-Rules.md](Operating-Rules.md). Edit that file when changing workspace behavior for all assistants.

Portable, reusable workflows live in [Skills](Skills). Skills contain no personal configuration; they resolve that from the ignored `Context/` directory or the environment.

The vault root and this directory each contain small `AGENTS.md` (Codex) and `CLAUDE.md` (Claude) entry points directing assistants to the shared rules. Start a local assistant in either the vault root or `Workspace/`; operations belong in `Workspace/`.

For sessions using uploaded files, provide `Operating-Rules.md` and the relevant context and project files explicitly. These entry points do not grant filesystem access or synchronize uploaded copies.

## User Interfaces

- ### Obsidian

- ### VScode

  - Claude Code
  - markdownlint

- ### Github

## System Interfaces

| target           | connector | note                                                                                           |
| ---------------- | --------- | ---------------------------------------------------------------------------------------------- |
| obsidian         | skill     | [kepano/obsidian-skills: Agent skills for Obsidian](https://github.com/kepano/obsidian-skills) |
| github           | mcp       |                                                                                                |
| google workspace | ?         | might be browser-mediated                                                                      |
| browser          | extension | [Claude in Chrome \| Claude](https://claude.com/chrome)                                        |
