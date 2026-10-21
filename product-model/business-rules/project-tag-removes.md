---
appliesTo:
- type: entity
  id: project-tag
  effect: removes
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

# The owning person removes their project tag

The owning person removes their project tag.
