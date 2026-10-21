---
kind: primary
routes:
  web: Browser
steps:
- text: The person clears the snapshot's name
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite removes the label from the snapshot
  kind: product
  entities:
  - entity: snapshot
    effect: changes
    facts:
    - Label
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Remove history label

## Trigger

A named snapshot no longer needs keeping.

## Outcome

The snapshot is ordinary again, and the next pruning may remove it if storage is over its limit.
