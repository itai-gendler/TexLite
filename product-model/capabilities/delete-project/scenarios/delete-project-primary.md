---
kind: primary
routes:
  web: Browser
steps:
- text: The owner confirms deleting the project
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite deletes the project
  kind: product
  entities:
  - entity: project
    effect: removes
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Delete project

## Trigger

The owner no longer needs the project.

## Outcome

The project disappears for everyone, with its files, compiled output, members, comments and snapshots. This cannot be undone.
