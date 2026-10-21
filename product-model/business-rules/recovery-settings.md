---
appliesTo:
- type: entity
  id: project
  effect: changes
  contexts:
  - place: web::writing::history
references:
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
permits:
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
- related:
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: user
  when:
  - entity: membership
    fact: Role
    is: Read & write
- related:
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
  when:
  - entity: membership
    fact: Role
    is: Read & write
---

# Only the project owner and members with Read & write access restore snapshots, including compiler settings

Restoring a whole snapshot also brings back its compiler settings, which only the owner can otherwise change.
