---
appliesTo:
- type: entity
  id: comment
  effect: removes
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

# Only its author deletes a comment

Other participants, the project owner included, cannot delete someone else's discussion.
