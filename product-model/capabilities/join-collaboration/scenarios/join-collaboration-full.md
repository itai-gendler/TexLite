---
kind: edge
routes:
  web: Browser
steps:
- text: The person opens the project workspace
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports the room capacity limit
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Wait when the room is full

## Trigger

Ten sessions are already active or admitted for the project.

## Outcome

The browser reports that the collaboration room is full and may retry later.
