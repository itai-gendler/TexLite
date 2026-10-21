---
kind: primary
routes:
  web: Browser
steps:
- text: The person edits the reference
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite saves the citation revision
  kind: product
  entities:
  - entity: citation
    effect: changes
    facts:
    - Key
    - Entry type
    - BibTeX
    - Title
    - Authors
    - Year
    - Revision
    - Modified
  contexts:
    web:
      place: web::writing::citations
  actor: user
---

# Edit a library entry

## Trigger

The person saves revised BibTeX for an inspected reference.

## Outcome

The citation text and metadata change and its revision advances.
