---
type: web
actors:
- visitor
- user
- administrator
entryPoints:
- web: /
- web: /project/:id
references:
- kind: code
  role: implementation
  target: src/client/App.tsx
- kind: code
  role: implementation
  target: src/client/routes.ts
---

# Web

The browser interface for shared LaTeX writing, personal libraries, and team administration. Entry paths are relative to the configured deployment mount point.
