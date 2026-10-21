---
kind: validation
routes:
  web: Browser
steps:
- text: The person selects an archive
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite reports the import problem
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Reject an unusable archive

## Trigger

A selected archive is invalid, exceeds an import limit, or contains no usable TeX main document.

## Outcome

Import fails without keeping a partial project.
