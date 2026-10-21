---
appliesTo:
- type: entity
  id: project
  effect: changes
  facts:
  - Latexmkrc
  contexts:
  - place: web::writing::project
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
  when:
  - entity: deployment
    fact: Project latexmkrc allowed
    is: true
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
  when:
  - entity: deployment
    fact: Project latexmkrc allowed
    is: true
---

# Only the project owner selects a project latexmkrc, and only where the deployment allows it

The option exists only when the deployment enables project latexmkrc files.
