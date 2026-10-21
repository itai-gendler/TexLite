---
kind: primary
routes:
  web: Browser
steps:
- text: The author confirms deleting their reply
  kind: actor
  entities:
  - entity: reply
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite deletes the reply
  kind: product
  entities:
  - entity: reply
    effect: removes
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Delete reply

## Trigger

The author no longer wants a reply in the discussion.

## Outcome

The reply disappears from the discussion for everyone; the comment and other replies stay.
