---
kind: primary
routes:
  web: Browser
steps:
- text: The person changes the tag's name or color
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
- text: TexLite saves the citation tag
  kind: product
  entities:
  - entity: citation-tag
    effect: changes
    facts:
    - Name
    - Color
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
---

# Edit citation tag

## Trigger

A citation tag needs a better name or color.

## Outcome

Every citation carrying the tag shows its new name and color.
