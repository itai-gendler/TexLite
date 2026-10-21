---
kind: edge
routes:
  web: Browser
steps:
- text: The person supplies the token
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::github
  actor: user
- text: TexLite reports the validation failure
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::github
  actor: user
---

# Report a GitHub connection failure

## Trigger

GitHub rejects the token or cannot be reached.

## Outcome

The connection is not replaced and the error is shown.
