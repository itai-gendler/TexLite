---
kind: primary
routes:
  web: Browser
steps:
- text: The person selects a citation
  kind: actor
  entities:
  - entity: citation
    effect: reads
    facts:
    - Key
    - BibTeX
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite inserts reference text into the file
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Import a saved reference into source

## Trigger

The person chooses Import from the in-project library.

## Outcome

The citation text is inserted with separating newlines and the library closes back to the source.

## Edge cases

- An existing key in the active file is refused without inserting a duplicate.
- Invalid or oversized bibliography text is reported before insertion.
