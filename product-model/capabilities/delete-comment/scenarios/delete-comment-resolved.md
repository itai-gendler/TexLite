---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms removal
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite removes the comment and replies
  kind: product
  entities:
  - entity: comment
    effect: removes
    from: Resolved
  - entity: reply
    effect: removes
    with: comment
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Delete a resolved comment

## Trigger

The person confirms removing their thread.

## Outcome

The thread, replies, and associated notifications are removed.
