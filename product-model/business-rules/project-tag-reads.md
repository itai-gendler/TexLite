---
appliesTo:
- type: entity
  id: project-tag
  effect: reads
references:
- kind: code
  role: implementation
  target: src/server/routes/projects.ts#registerProjectCatalogRoutes
permits:
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
---

# The owning person reads their project tag

The owning person reads their project tag.
