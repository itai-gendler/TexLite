---
kind: primary
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
- text: TexLite starts the collaboration session
  kind: product
  entities:
  - entity: collaboration-session
    effect: creates
    facts:
    - Participant
    - Permission
    - Active file
    - Cursor
    - Connection
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Join a live workspace

## Trigger

A person opens a project workspace.

## Outcome

The room displays active participants, permissions, active files, and cursors.
