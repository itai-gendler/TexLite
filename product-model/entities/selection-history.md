---
domain: history
references:
- kind: code
  role: implementation
  target: src/server/editHistory.ts#ProjectEditHistoryService
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
- kind: code
  role: implementation
  target: src/client/SelectionHistoryDialog.tsx
---

# Selection history

The author-attributed editing trail shown for a selected passage.

## Information kept

- **File path** — The source file.
- **Contributors** — People whose durable edits affected the passage.
- **Time** — The editing window’s latest change time.
- **Operation** — Ordinary editing or formatting.
- **Passage** — Reconstructed selected text and comparison with the older state.
- **Boundary** — A replacement, missing record, or retention point beyond which attribution stops.
- **Storage** — The project-wide payload usage.
