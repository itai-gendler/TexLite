---
appliesTo:
- type: entity
  id: snapshot
  effect: removes
references:
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
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
- unattended: true
---

# Only the project owner deletes snapshots; TexLite prunes ordinary ones

The owner deletes one snapshot or clears them all. Automatic pruning removes only ordinary snapshots.
