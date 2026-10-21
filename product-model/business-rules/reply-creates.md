---
appliesTo:
- type: entity
  id: reply
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
permits:
- related:
  - verb: contains
    entity: comment
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: contains
    entity: comment
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
- related:
  - verb: contains
    entity: comment
  - verb: contains
    entity: project
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: contains
    entity: comment
  - verb: contains
    entity: project
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
---

# The owner and all members reply to comments

Read only members can take part in every discussion.
