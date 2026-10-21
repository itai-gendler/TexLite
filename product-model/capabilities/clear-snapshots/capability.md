---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
- kind: code
  role: implementation
  target: src/client/HistoryDialog.tsx
domain: history
---

# Clear snapshots

Permanently delete every snapshot of a project; the current source and selection history stay.
