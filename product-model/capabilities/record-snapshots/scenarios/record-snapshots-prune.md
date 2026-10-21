---
kind: unattended
routes:
  web: Browser
steps:
- text: The snapshots are over their count or storage limit
  kind: condition
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  unattended: true
- text: TexLite removes the oldest ordinary snapshots
  kind: product
  entities:
  - entity: snapshot
    effect: removes
  contexts:
    web:
      place: web::writing::history
---

# Prune ordinary snapshots

## Trigger

A save brings the project's snapshots over their count or storage limit.

## Outcome

The oldest ordinary snapshots are removed until the project is within its limits; the first, labeled and latest snapshots are kept, so the storage limit is a soft one.
