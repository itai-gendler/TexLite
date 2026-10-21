---
appliesTo:
- type: entity
  id: mention
  effect: changes
  to: Read
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
permits:
- related:
  - verb: receives
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: receives
    entity: account
  - verb: uses
    entity: administrator
- unattended: true
---

# Recipients acknowledge their mentions and TexLite acknowledges those in resolved discussions

Recipients acknowledge their own mentions. Resolving a discussion automatically acknowledges its existing unread notifications for all recipients.
