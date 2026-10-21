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

# Cancel compile

Stop the current compile for the selected root and discard its pending follow-up work.
