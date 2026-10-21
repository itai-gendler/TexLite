---
domain: comments
references:
- kind: code
  role: implementation
  target: src/server/commentMentions.ts
- kind: code
  role: implementation
  target: src/client/workspace/useProjectMentions.ts
---

# Mention

A personal notification linking an exact username mention to a thread or reply.

## Information kept

- **Target** — The discussion item and source file.
- **Sender** — The person who mentioned the recipient.
- **Created** — When the mention was generated.
- **Read reason** — Opened, manually marked, or resolved with the thread.

## States

### Unread

The recipient has not read the notification.

### Read

The notification has been acknowledged or its thread resolved.
