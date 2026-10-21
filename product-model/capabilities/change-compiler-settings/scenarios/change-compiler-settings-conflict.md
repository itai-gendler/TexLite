---
kind: edge
routes:
  web: Browser
steps:
- text: The person submits the edited fields
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports the conflict
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Reject a stale settings form

## Trigger

A changed field no longer matches the value originally loaded by the browser.

## Outcome

The save reports a conflict without overwriting the newer settings.
