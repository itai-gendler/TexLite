---
appliesTo:
- type: entity
  id: comment
  effect: changes
  facts:
  - Content
  - Edited
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
permits:
- related:
  - verb: authors
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: authors
    entity: account
  - verb: uses
    entity: administrator
---

# Only its author edits a comment

Other participants can reply to a discussion but cannot change its opening message.
