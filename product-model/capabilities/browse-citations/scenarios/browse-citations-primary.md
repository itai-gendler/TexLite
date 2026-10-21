---
kind: primary
routes:
  web: Browser
steps:
- text: The person searches the library or picks a tag
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite lists the matching saved citations with their citation tags
  kind: product
  entities:
  - entity: citation
    effect: reads
    facts:
    - Key
    - Entry type
    - BibTeX
    - Title
    - Authors
    - Year
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

# Browse citations

## Trigger

The person opens their citation library.

## Outcome

The library shows only this person's citations, matched by key, title, author or year and narrowed to the chosen tag.
