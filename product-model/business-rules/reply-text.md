---
appliesTo:
- type: entity
  id: reply
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

# Only its author edits a reply

A reply keeps its author's words unless that author edits it.
