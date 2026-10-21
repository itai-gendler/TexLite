---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms replacement
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite replaces the file and adjusts comment anchors
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
  - entity: comment
    effect: changes
    facts:
    - Quote
    - Anchor
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Replace an existing text file

## Trigger

The first upload meets an existing path and the person explicitly confirms replacement.

## Outcome

The new contents replace the old text, comments are re-anchored, and collaborators see the change.

## Edge cases

- A directory cannot be replaced by a file.
- An upload over the applicable size limit is rejected.
