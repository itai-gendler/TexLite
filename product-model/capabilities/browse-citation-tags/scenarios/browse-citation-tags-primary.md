---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens Manage tags in their library
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
- text: TexLite lists the person's citation tags with their colors
  kind: product
  entities:
  - entity: citation-tag
    effect: reads
    facts:
    - Name
    - Color
  contexts:
    web:
      place: web::writing::citation-tags
  actor: user
---

# Browse citation tags

## Trigger

The person wants to tidy the tags they use for citations.

## Outcome

Only this person's citation tags are listed, ready to rename, recolor or delete.
