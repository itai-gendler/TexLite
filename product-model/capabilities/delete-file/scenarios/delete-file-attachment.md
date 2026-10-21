---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms deletion
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite removes the attachment
  kind: product
  entities:
  - entity: attachment
    effect: removes
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Delete an attachment

## Trigger

The person confirms deleting an attachment.

## Outcome

The attachment is removed from the source tree.
