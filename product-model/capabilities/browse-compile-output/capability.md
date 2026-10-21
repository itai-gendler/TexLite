---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/compile.ts#registerCompileRoutes
- kind: code
  role: implementation
  target: src/client/workspace/CompileOutput.tsx
- kind: code
  role: implementation
  target: src/client/workspace/useProjectCompilation.ts
---

# Browse compile output

Show the latest compile job status, transcript, diagnostics, retained PDF, and artifact list for the selected root.
