---
references:
- kind: code
  role: implementation
  target: src/client/HistoryDialog.tsx
---

# History

The project's automatic snapshots and the edit history of selected passages: browsing, comparing, labeling, restoring and clearing them.

## Boundary

Owns snapshots and the edit history of passages; it does not own Git commits.
