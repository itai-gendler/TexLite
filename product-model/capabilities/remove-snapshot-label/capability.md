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

# Remove history label

Remove a snapshot's name, so automatic pruning treats it like any other.
