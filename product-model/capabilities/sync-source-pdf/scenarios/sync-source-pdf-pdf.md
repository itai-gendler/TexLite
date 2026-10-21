---
kind: primary
routes:
  web: Browser
steps:
- text: The person asks where the current source line appears in the PDF
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

# Find the PDF location for source

## Trigger

The person asks where the current line of the selected main document appears in the PDF.

## Outcome

The corresponding destination is revealed when SyncTeX information is available.

## Edge cases

- Missing SyncTeX data or an unmapped location reports that navigation is unavailable.
- Forward navigation is offered for the active root; a secondary source tab does not initiate it.
