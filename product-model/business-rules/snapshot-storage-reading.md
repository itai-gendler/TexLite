---
appliesTo:
- type: entity
  id: snapshot
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

# Only the project owner sees snapshot storage use

Members browse snapshots but not their storage use.
