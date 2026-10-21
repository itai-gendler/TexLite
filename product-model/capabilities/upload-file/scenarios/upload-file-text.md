---
kind: alternate
routes:
  web: Browser
steps:
- text: The person selects the upload
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the file
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

# Upload text source

## Trigger

The selected upload is editable text.

## Outcome

The new source is available in the editor and live collaboration.
