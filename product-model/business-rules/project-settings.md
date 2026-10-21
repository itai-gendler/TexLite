---
appliesTo:
- type: entity
  id: project
  effect: changes
  facts:
  - Name
  - Icon
  - Owner
  - Main document
  - Engine
  - Latexmkrc
  - ChkTeX enabled
  contexts:
  - place: web::writing::project
  - place: web::writing::projects
references:
- kind: code
  role: implementation
  target: src/server/routes/projects.ts#registerProjectCatalogRoutes
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
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

# Only the project owner renames a project or changes its icon, settings or owner

Members, Read & write included, cannot change the project's name, icon, main document, engine, latexmkrc, ChkTeX setting or owner.
