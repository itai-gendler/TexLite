---
kind: primary
routes:
  web: Browser
steps:
- text: The person requests the original resource
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::writing::project
- text: TexLite downloads the attachment bytes
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: reads
    facts:
    - Path
    - Content
    - Size
  contexts:
    web:
      place: web::writing::project
---

# Download an original resource

## Trigger

The person requests Download in the resource preview.

## Outcome

The original bytes are downloaded even when no inline preview is supported.
