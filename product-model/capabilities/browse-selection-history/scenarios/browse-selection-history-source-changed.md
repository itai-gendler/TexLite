---
kind: edge
routes:
  web: Browser
steps:
- text: The person requests passage history
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite reports the revision conflict
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Retry a changed passage

## Trigger

The submitted source revision differs from saved source after flushing.

## Outcome

The request reports a source-change conflict; the person can inspect a newly selected current passage.
