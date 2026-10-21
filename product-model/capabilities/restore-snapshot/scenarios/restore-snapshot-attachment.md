---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms a retained resource
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite restores the attachment
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Files
    - Fingerprint
  - entity: attachment
    effect: changes
    facts:
    - Content
    - Size
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Restore one retained attachment

## Trigger

The person selects a retained attachment.

## Outcome

The selected attachment bytes are restored without decoding them as text.
