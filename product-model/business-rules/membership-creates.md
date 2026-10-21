---
appliesTo:
- type: entity
  id: membership
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
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
---

# Only the project owner shares a project

The owner shares with an existing, enabled account and chooses Read only or Read & write.
