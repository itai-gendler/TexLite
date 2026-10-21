---
appliesTo:
- type: entity
  id: file
- type: entity
  id: folder
- type: entity
  id: project
  facts:
  - Main document
references:
- kind: code
  role: implementation
  target: src/server/routes/projectFiles.ts#registerProjectFileRoutes
- kind: code
  role: implementation
  target: src/server/latexRoot.ts
---

# The selected main document remains a valid root

The configured root cannot be deleted with its containing folder and keeps a .tex extension on rename. Root selection requires a documentclass declaration, with the sole-.tex-file fallback.
