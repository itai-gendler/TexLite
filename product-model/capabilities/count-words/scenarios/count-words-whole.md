---
kind: primary
routes:
  web: Browser
steps:
- text: The person requests document statistics
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite counts file content
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

# Count the full document

## Trigger

The person requests full-document statistics.

## Outcome

The selected root and included source are counted after live edits have been saved.
