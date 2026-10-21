---
kind: primary
result: achieved
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
  capability: create-file
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
  capability: create-file
- text: The person edits file content
  kind: actor
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
  capability: edit-file
- text: TexLite saves the file and remaps comment anchors
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
    - Anchor
    - Quote
  contexts:
    web:
      place: web::writing::project
  actor: user
  capability: edit-file
---

# Write in a new file

## Trigger

The person creates a source file.

## Outcome

The new file is selected and its first edit is saved.
