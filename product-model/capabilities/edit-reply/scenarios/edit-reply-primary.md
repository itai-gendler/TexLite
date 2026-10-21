---
kind: primary
routes:
  web: Browser
steps:
- text: The author revises their reply
  kind: actor
  entities:
  - entity: reply
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the reply with its edited time
  kind: product
  entities:
  - entity: reply
    effect: changes
    facts:
    - Content
    - Edited
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Edit reply

## Trigger

The author wants to correct or clarify their reply.

## Outcome

Everyone sees the revised reply, marked as edited. Only people newly mentioned in it are notified.
