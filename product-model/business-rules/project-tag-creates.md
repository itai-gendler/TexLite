---
appliesTo:
- type: entity
  id: project-tag
  effect: creates
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

# The owning person creates their project tag

The owning person creates their project tag.
