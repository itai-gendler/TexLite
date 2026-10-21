---
kind: primary
routes:
  web: Browser
steps:
- text: The author revises their message
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the comment with its edited time
  kind: product
  entities:
  - entity: comment
    effect: changes
    facts:
    - Content
    - Edited
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Edit comment

## Trigger

The author wants to correct or clarify their comment.

## Outcome

Everyone sees the revised message, marked as edited. Only people newly mentioned in it are notified.
