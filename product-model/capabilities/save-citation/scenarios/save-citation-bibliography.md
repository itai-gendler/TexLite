---
kind: alternate
routes:
  web: Browser
steps:
- text: The person selects an entry in the file
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
      place: web::writing::project
  actor: user
---

# Save an entry from the current bibliography

## Trigger

The person chooses a parsed entry from an open .bib file.

## Outcome

The selected entry is saved to the personal library; the source file is unchanged, and the saved entry’s tag editor opens.
