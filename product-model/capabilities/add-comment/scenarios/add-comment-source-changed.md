---
kind: edge
routes:
  web: Browser
steps:
- text: The person submits the selected passage
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports changed source
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Retry a comment against current source

## Trigger

The source changed after the browser captured the selection.

## Outcome

The message is not attached to offsets from a different revision; the person can reselect and retry.
