---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Restore in the archived project's actions
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite returns the project to this person's active projects in their project organization
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

# Unarchive project

## Trigger

The person needs an archived project again.

## Outcome

The project is back in this person's active projects; other participants' catalogs are unchanged.
