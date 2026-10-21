---
kind: alternate
routes:
  web: Browser
steps:
- text: The person chooses a folder and name, or drags the item onto a folder
  kind: actor
  entities:
  - entity: folder
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite changes folder and descendant paths
  kind: product
  entities:
  - entity: folder
    effect: changes
    facts:
    - Path
  - entity: file
    effect: changes
    facts:
    - Path
    - Language
  - entity: attachment
    effect: changes
    facts:
    - Path
    - Preview type
  - entity: comment
    effect: changes
    facts:
    - File path
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Move or rename a folder

## Trigger

The person chooses Move or rename for a folder, or drags it onto another folder.

## Outcome

The folder and descendant paths move together without ending collaboration.

## Edge cases

- A folder cannot be moved into itself or its descendants.
