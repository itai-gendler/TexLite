---
kind: unattended
routes:
  web: Browser
steps:
- text: A discussion has become resolved
  kind: condition
  unattended: true
  entities: []
  contexts:
    web:
      place: web::writing::project
- text: TexLite acknowledges existing unread mentions in the resolved discussion
  kind: product
  entities:
  - entity: mention
    effect: changes
    from: Unread
    to: Read
    facts:
    - Read reason
  contexts:
    web:
      place: web::writing::project
---

# Acknowledge mentions after resolution

## Trigger

A discussion becomes resolved with existing unread notifications.

## Outcome

TexLite marks all of those notifications Read with reason resolved. Reopening the discussion leaves them Read.
