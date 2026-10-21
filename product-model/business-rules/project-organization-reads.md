---
appliesTo:
- type: entity
  id: project-organization
  effect: reads
references:
- kind: code
  role: implementation
  target: src/server/routes/projects.ts#registerProjectCatalogRoutes
permits:
- related:
  - verb: keeps
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: keeps
    entity: account
  - verb: uses
    entity: administrator
---

# Each person sees only their own archive status and tags

Another participant's archive and tags are never shown.
