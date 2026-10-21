---
kind: edge
routes:
  web: Browser
steps:
- text: The person continues the current draft
  kind: actor
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reconnects the collaboration session and persists file content
  kind: product
  entities:
  - entity: collaboration-session
    effect: changes
    facts:
    - Connection
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Recover edits after a transient disconnect

## Trigger

The browser loses its live connection with unsent edits.

## Outcome

The workspace reconnects, and the edits made while offline are merged into the shared source and saved.

## Edge cases

- When the source was replaced meanwhile, by a restore or checkout, the workspace reloads the new source instead.
