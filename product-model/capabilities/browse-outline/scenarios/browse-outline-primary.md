---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens the outline
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite lists the document's headings in reading order across its included files
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

# Browse outline

## Trigger

The person wants to move around a long document.

## Outcome

Headings appear in the order a reader meets them, including those in \input and \include files, and choosing one opens its source location.
