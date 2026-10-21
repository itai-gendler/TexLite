---
kind: primary
routes:
  web: Browser
steps:
- text: The person supplies a directory name
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite creates the folder
  kind: product
  entities:
  - entity: folder
    effect: creates
    facts:
    - Path
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Create folder

## Trigger

The person wants to organize the source tree.

## Outcome

The folder, empty for now, appears in every open workspace of the project.
