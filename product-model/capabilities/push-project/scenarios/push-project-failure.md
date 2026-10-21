---
kind: edge
routes:
  web: Browser
steps:
- text: The person requests a push
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite reports the push failure
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Report a failed push

## Trigger

GitHub rejects the credential or the remote operation fails.

## Outcome

The panel reports the failure; local source and commits remain.
