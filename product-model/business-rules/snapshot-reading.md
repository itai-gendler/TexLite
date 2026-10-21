---
appliesTo:
- type: entity
  id: snapshot
  effect: reads
  facts:
  - Created
  - Author
  - Reason
  - Label
  - Changed paths
  - Files
  - Compiler settings
  - Fingerprint
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

# The owner and all members browse and compare snapshots

Everyone in the project can see its snapshots and compare them with the current source.
