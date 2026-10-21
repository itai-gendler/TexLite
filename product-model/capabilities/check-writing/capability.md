---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/projects.ts#registerProjectCatalogRoutes
- kind: code
  role: implementation
  target: src/client/workspace/useSpellCheck.ts
- kind: code
  role: implementation
  target: src/client/workspace/useChktex.ts
---

# Check writing

Inspect spelling, grammar, and enabled ChkTeX diagnostics for eligible source. Harper and ChkTeX are optional host tools.
