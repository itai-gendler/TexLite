---
kind: primary
routes:
  web: Browser
steps:
- text: The person closes the workspace or returns to Projects
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite ends the collaboration session
  kind: product
  entities:
  - entity: collaboration-session
    effect: removes
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Leave collaboration

## Trigger

The person stops working on the project.

## Outcome

The person no longer appears among the active participants, and their place counts toward the room's limit no more.
