---
kind: primary
routes:
  web: Browser
steps:
- text: The person selects file text and writes a message
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite creates the comment
  kind: product
  entities:
  - entity: comment
    effect: creates
    to: Open
    facts:
    - Content
    - Author
    - File path
    - Quote
    - Anchor
    - Created
    - Edited
    - Resolution
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Comment on selected source

## Trigger

The person selects a passage and submits a message.

## Outcome

An Open thread retains the source quote and anchor, and other workspaces refresh their discussions.

## Edge cases

- Messages must contain nonblank text of at most 5,000 characters.
