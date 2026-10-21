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
  target: src/client/workspace/useProjectCompilation.ts
---

# Compile project

Compile the selected main document from a consistent copy of the saved source, while everyone keeps editing.
