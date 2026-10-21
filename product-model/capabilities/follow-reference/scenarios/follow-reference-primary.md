---
kind: primary
routes:
  web: Browser
steps:
- text: The person Ctrl- or Cmd-clicks a cited key or a referenced label
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite finds the bibliography entry or label definition and opens its file at that place
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Follow reference

## Trigger

The person wants to see what a \cite or \ref points to.

## Outcome

The target source is opened; a missing target produces a message.
