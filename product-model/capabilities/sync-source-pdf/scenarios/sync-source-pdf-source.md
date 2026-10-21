---
kind: alternate
routes:
  web: Browser
steps:
- text: The person asks for the source of a place in the PDF
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite locates the matching source and compiled page
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
  - entity: compile-job
    effect: reads
    facts:
    - Root
    - PDF
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Find the source location for PDF

## Trigger

The person double-clicks a place in the PDF, or asks for its source location.

## Outcome

The corresponding source location is revealed, which can be in an included file rather than the root.

## Edge cases

- Missing SyncTeX data or an unmapped location reports that navigation is unavailable.
