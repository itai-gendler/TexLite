---
kind: alternate
routes:
  web: Browser
steps:
- text: The person adds the recipient to the edited message
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite refreshes the mention
  kind: product
  entities:
  - entity: mention
    effect: changes
    from: Read
    to: Unread
    facts:
    - Sender
    - Created
    - Read reason
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Renew a previous mention

## Trigger

The person adds back a recipient removed in an earlier edit.

## Outcome

The notification becomes unread again with the new mention time.
