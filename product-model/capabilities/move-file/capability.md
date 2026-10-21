---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/projectFiles.ts#registerProjectFileRoutes
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
- kind: code
  role: implementation
  target: src/client/workspace/useProjectFiles.ts
---

# Move or rename file

Give a file, attachment or folder a new name or folder, while open workspaces and comments follow it.
