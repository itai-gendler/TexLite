---
appliesTo:
- type: entity
  id: project-organization
  effect: changes
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

# Each person archives and tags projects only for themselves

Archive status and tags are personal: changing them never changes another participant's catalog.
