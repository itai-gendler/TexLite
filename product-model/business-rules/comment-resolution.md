---
appliesTo:
- type: entity
  id: comment
  effect: changes
  facts:
  - Resolution
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
permits:
- related:
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
- related:
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
    entity: project
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
---

# The owner and all members resolve and reopen comments

Resolving is not limited to the author: anyone in the project, Read only members included, can resolve or reopen a discussion.
