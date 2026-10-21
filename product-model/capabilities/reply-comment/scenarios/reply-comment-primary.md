---
kind: primary
routes:
  web: Browser
steps:
- text: The person submits a response
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite adds the reply to the comment
  kind: product
  entities:
  - entity: comment
    effect: reads
    facts: []
  - entity: reply
    effect: creates
    facts:
    - Content
    - Author
    - Created
    - Edited
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Reply to comment

## Trigger

The person answers a discussion.

## Outcome

The reply appears under the comment in every open workspace; people mentioned in it are notified.
