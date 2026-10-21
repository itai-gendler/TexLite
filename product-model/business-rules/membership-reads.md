---
appliesTo:
- type: entity
  id: membership
  effect: reads
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

# The owner and all members see who a project is shared with

Every participant sees the project's members and their access.
