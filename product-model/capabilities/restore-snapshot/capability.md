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

# Restore snapshot

Restore one file, or the whole project with its compiler settings, from a snapshot.
