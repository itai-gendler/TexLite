---
appliesTo:
- type: entity
  id: collaboration-session
  effect: reads
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
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

# Only the owner and members see who is in a project

Active participants, their access, active files and cursors are visible to everyone in the project.
