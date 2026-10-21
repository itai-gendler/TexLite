---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/compile.ts#registerCompileRoutes
- kind: code
  role: implementation
  target: src/server/synctex.ts
- kind: code
  role: implementation
  target: src/client/workspace/useSyncTeX.ts
---

# Sync source and PDF

Navigate between source and the retained PDF using SyncTeX for the selected root.
