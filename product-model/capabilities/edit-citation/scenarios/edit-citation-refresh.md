---
kind: alternate
routes:
  web: Browser
steps:
- text: The person selects the source reference
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
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
      place: web::writing::project
  actor: user
---

# Refresh from bibliography text

## Trigger

The person chooses Update on an entry already in their library.

## Outcome

The inspected reference is replaced from the .bib text and keeps its existing tags.
