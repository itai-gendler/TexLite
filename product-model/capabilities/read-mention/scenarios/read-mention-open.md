---
kind: primary
routes:
  web: Browser
steps:
- text: The person follows the mention
  kind: actor
  entities:
  - entity: mention
    effect: reads
    facts:
    - Target
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reveals the discussion and marks the mention read
  kind: product
  entities:
  - entity: comment
    effect: reads
    facts:
    - Content
    - Author
    - File path
    - Quote
    - Anchor
    - Created
    - Edited
    - Resolution
  - entity: reply
    effect: reads
    facts:
    - Content
    - Author
    - Created
    - Edited
  - entity: mention
    effect: changes
    from: Unread
    to: Read
    facts:
    - Read reason
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Read a located mention

## Trigger

The person follows a mention notification.

## Outcome

The workspace locates the exact thread or reply and then marks that notification read.

## Edge cases

- A target that cannot be found stays unread.
