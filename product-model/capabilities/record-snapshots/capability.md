---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
- kind: code
  role: implementation
  target: src/server/historyRetention.ts
- kind: code
  role: implementation
  target: src/server/app.ts
domain: history
---

# Record snapshots

Take a snapshot automatically whenever files change, and keep snapshots within the configured limits.
