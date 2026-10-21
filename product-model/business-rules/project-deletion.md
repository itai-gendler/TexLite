---
appliesTo:
- type: entity
  id: project
  effect: removes
  contexts:
  - place: web::writing::projects
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

# Only the project owner deletes a project

Members, Read & write included, cannot delete a project.
