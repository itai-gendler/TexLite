---
appliesTo:
- type: entity
  id: snapshot
- type: entity
  id: selection-history
references:
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
- kind: code
  role: implementation
  target: src/server/editHistory.ts#ProjectEditHistoryService
---

# Automatic pruning never removes protected snapshots

The first snapshot, labeled snapshots and the latest one are protected from automatic pruning, so the storage limit is a soft limit. The owner can still delete any snapshot. Selection history has its own, separate storage budget.
