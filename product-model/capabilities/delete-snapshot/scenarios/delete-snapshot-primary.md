---
kind: primary
routes:
  web: Browser
steps:
- text: The owner confirms Delete snapshot
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite deletes the snapshot
  kind: product
  entities:
  - entity: snapshot
    effect: removes
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Delete a snapshot

## Trigger

The owner no longer needs one snapshot.

## Outcome

The snapshot is gone; the project's files and selection history are unchanged.
