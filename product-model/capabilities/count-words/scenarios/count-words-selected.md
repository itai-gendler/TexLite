---
kind: alternate
routes:
  web: Browser
steps:
- text: The person selects source to count
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
- text: TexLite returns the selection counts
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Count a selected passage

## Trigger

The person selects text from .tex, .sty, or .cls source.

## Outcome

Counts apply to the selected source rather than the whole document.
