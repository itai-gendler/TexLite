---
kind: primary
routes:
  web: Browser
steps:
- text: The person clears a tag in the citation's tag editor
  kind: actor
  entities:
  - entity: citation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite saves the citation without that citation tag
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

# Remove citation tag

## Trigger

The person opens Tags for a saved citation, clears a tag and saves.

## Outcome

The citation no longer carries the tag; the tag itself stays in the library. If the citation was changed elsewhere since it was opened, the save is refused.
