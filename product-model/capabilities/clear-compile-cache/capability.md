---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/compile.ts#registerCompileRoutes
- kind: code
  role: implementation
  target: src/server/compiler.ts
- kind: code
  role: implementation
  target: src/client/workspace/CompileOutput.tsx
---

# Clear compile cache

Discard incremental compile cache for the selected root while retaining the successful PDF.
