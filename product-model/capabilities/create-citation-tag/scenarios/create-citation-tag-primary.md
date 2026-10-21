---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters a tag name and picks a color
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
- text: TexLite creates the citation tag
  kind: product
  entities:
  - entity: citation-tag
    effect: creates
    facts:
    - Name
    - Color
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
---

# Create citation tag

## Trigger

The person wants a new way to group their citations.

## Outcome

The tag is available for this person's citations. A name the person already uses, in any letter case, is refused.
