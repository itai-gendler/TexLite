---
appliesTo:
- type: entity
  id: reply
  effect: removes
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
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
---

# Deleting a reply also requires current access to its project

An author who is no longer the owner or a member of the project cannot delete their replies there. This holds together with the rule that only the author deletes a reply.
