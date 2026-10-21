---
kind: primary
routes:
  web: Browser
steps:
- text: The owner confirms Clear snapshots
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite deletes every snapshot of the project
  kind: product
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: snapshot
    effect: removes
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Clear all snapshots

## Trigger

The owner wants to free the storage snapshots use.

## Outcome

No snapshots remain, and the storage they used is freed; the project's files and selection history are unchanged.
