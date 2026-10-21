---
appliesTo:
- type: entity
  id: selection-history
  effect: reads
  facts:
  - Storage
references:
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
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

# Only the project owner sees selection history storage

Members see the trail itself but not its project-wide storage use.
