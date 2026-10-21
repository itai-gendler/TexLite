---
kind: primary
result: achieved
routes:
  web: Browser
steps:
- text: The person supplies the reference
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
  capability: save-citation
- text: TexLite saves the citation and opens its tag editor
  kind: product
  entities:
  - entity: citation
    effect: creates
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
  contexts:
    web:
      place: web::writing::citations
  actor: user
  capability: save-citation
- text: The person selects an additional label
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
  capability: assign-citation-tag
- text: TexLite saves the citation with the chosen tags
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
  capability: assign-citation-tag
---

# Save and organize a citation

## Trigger

The person saves a new BibTeX reference.

## Outcome

The tag editor opens for that saved reference, and the person applies an existing tag.
