---
appliesTo:
- type: entity
  id: comment
- type: entity
  id: mention
references:
- kind: code
  role: implementation
  target: src/server/commentMentions.ts
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
---

# Resolving a discussion acknowledges its existing unread mentions

All existing unread notifications in that discussion become read with reason resolved. Reopening leaves those notifications read.
