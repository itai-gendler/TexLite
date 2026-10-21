---
kind: primary
routes:
  web: Browser
steps:
- text: The person selects another tag in the citation's tag editor
  kind: actor
  entities:
  - entity: citation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite saves the citation with the added citation tag
  kind: product
  entities:
  - entity: citation
    effect: changes
    facts:
    - Tags
    - Revision
    - Modified
  - entity: citation-tag
    effect: reads
    facts:
    - Name
    - Color
  contexts:
    web:
      place: web::writing::citations
  actor: user
---

# Assign citation tag

## Trigger

The person opens Tags for a saved citation, selects a tag and saves.

## Outcome

The citation carries the tag and can be found with that tag's filter. If the citation was changed elsewhere since it was opened, the save is refused.
