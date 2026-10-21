---
kind: alternate
routes:
  web: Browser
steps:
- text: The person selects text to format
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite applies formatted file text
  kind: product
  entities:
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

# Format only a selected passage

## Trigger

The person selects a source passage and requests formatting.

## Outcome

Only the selection is reformatted, retaining its surrounding indentation.
