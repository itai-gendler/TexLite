---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms deleting the tag
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
- text: TexLite deletes the citation tag
  kind: product
  entities:
  - entity: citation-tag
    effect: removes
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
---

# Delete citation tag

## Trigger

The person no longer needs a citation tag.

## Outcome

The tag disappears from every citation in the library; the citations themselves stay.
