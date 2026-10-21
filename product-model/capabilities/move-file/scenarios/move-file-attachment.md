---
kind: alternate
routes:
  web: Browser
steps:
- text: The person chooses a folder and name, or drags the item onto a folder
  kind: actor
  entities:
  - entity: folder
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite changes the attachment path
  kind: product
  entities:
  - entity: attachment
    effect: changes
    facts:
    - Path
    - Preview type
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Move or rename an attachment

## Trigger

The person chooses Move or rename for an attachment, or drags it onto another folder.

## Outcome

The attachment keeps its bytes at the new path.
