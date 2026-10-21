---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
- kind: code
  role: implementation
  target: src/server/editHistory.ts#ProjectEditHistoryService
- kind: code
  role: implementation
  target: src/client/SelectionHistoryDialog.tsx
domain: history
---

# Clear selection history

Clear the selection history trail after saving pending edits.
