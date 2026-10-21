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
- text: TexLite replaces the attachment
  kind: product
  entities:
  - entity: attachment
    effect: changes
    facts:
    - Content
    - Size
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Replace an attachment

## Trigger

The person explicitly confirms replacement of an existing attachment.

## Outcome

The bytes are replaced and the source tree refreshes.
