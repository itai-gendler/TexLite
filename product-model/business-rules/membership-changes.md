---
appliesTo:
- type: entity
  id: membership
  effect: changes
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

# Only the project owner changes a member's access

Switching a member between Read only and Read & write takes effect in their open sessions.
