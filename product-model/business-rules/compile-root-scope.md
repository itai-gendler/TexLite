---
appliesTo:
- type: entity
  id: compile-job
references:
- kind: code
  role: implementation
  target: src/server/compiler.ts
- kind: code
  role: implementation
  target: src/server/routes/compile.ts#registerCompileRoutes
---

# Compile work and retained results are scoped to one root

An identical active request shares its work; only the latest different pending generation is retained per root. Independent roots have separate retained PDFs and caches within global capacity.
