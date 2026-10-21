---
kind: validation
routes:
  web: Browser
steps:
- text: The person submits a new path
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports that the path exists
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Keep an existing file

## Trigger

The chosen path already exists.

## Outcome

Creation is refused without replacing the existing contents.
