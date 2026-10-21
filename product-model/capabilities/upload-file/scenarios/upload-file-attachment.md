---
kind: primary
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
- text: TexLite saves the attachment
  kind: product
  entities:
  - entity: attachment
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Preview type
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Upload an attachment

## Trigger

The person selects a local attachment and destination folder.

## Outcome

The attachment is saved and other sessions refresh the source tree.
