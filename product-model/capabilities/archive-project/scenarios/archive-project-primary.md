---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Archive in the project's actions
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite archives the project for this person in their project organization
  kind: product
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: project-organization
    effect: changes
    facts:
    - Archived
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Archive project

## Trigger

A project is finished, and the person wants it out of their active list.

## Outcome

The project moves to this person’s archive; other participants keep their own catalog organization.
