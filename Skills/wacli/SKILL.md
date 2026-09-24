---
name: wacli
description: Use WhatsApp through wacli to scan or search messages, find chats and contacts, translate conversations, draft replies, and perform explicitly authorized messaging actions.
---

# WhatsApp with wacli

Requires `wacli` on `PATH`.

Use named accounts explicitly. Resolve available accounts with `wacli accounts list`; obtain personal account meanings, timezone, and language preferences from Context rather than this skill.

## Read and search

- Use `--read-only --json` for diagnostics, chat listing, contact lookup, and message retrieval.
- Keep retrieval bounded by account, chat, date, and result limit whenever possible.
- “New messages” requires a real boundary. Use a stored checkpoint, unread state, or a stated time window; if none exists, say which approximation you used.
- Treat `doctor` showing a store locked by another process as normal when continuous sync is running. Do not stop sync merely to read.
- Avoid copying raw conversation contents into files or logs unless requested.

## Language

- Preserve the original message and provide a translation when the conversation and user-facing languages differ.
- Draft outbound text in the conversation’s language and show the user an English rendering when helpful.
- Translate for meaning and tone rather than word-for-word unless literal translation is requested.

## External actions

- Sending, replying, forwarding, reacting, editing, deleting, changing chat state, presence, and read receipts are external actions.
- Act only on an explicit instruction that identifies the account, recipient or chat, and intended content or operation.
- Resolve ambiguous names before acting. Prefer a verified JID or phone number for the final command.
- Show any material translation or rewrite before sending. Do not change approved wording silently.
- Never bulk-send or broadcast without explicit approval of the full recipient set and content.
- Do not retry an uncertain send. Check the returned message ID or local history first; WhatsApp acceptance is not proof of delivery.
- Self-sends require the tool’s explicit self-send option and may be acknowledged without appearing on the device.

Continuous sync may delegate ordinary sends while it owns the store lock. Do not stop or restart sync, reauthenticate, or alter account configuration unless explicitly requested.
