---
kind: primary
routes:
  web: Browser
steps:
- text: The person supplies a new path
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite creates the empty file and opens it in the editor
  kind: product
  entities:
  - entity: file
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Language
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Create file

## Trigger

The person adds a new source file to the project.

## Outcome

The empty file is created and immediately opened for editing.
