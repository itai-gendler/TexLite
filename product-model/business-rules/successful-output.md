---
appliesTo:
- type: entity
  id: compile-job
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

# Only successful compilation replaces the retained PDF

Queued, running, failed, and cancelled work leave the last successful result visible. Successful results based on older source are marked accordingly.
