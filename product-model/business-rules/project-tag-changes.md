---
appliesTo:
- type: entity
  id: project-tag
  effect: changes
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

# The owning person changes their project tag

The owning person changes their project tag.
