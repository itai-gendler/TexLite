---
kind: primary
routes:
  web: Browser
steps:
- text: The person includes the username in the message
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite creates the mention
  kind: product
  entities:
  - entity: mention
    effect: creates
    to: Unread
    facts:
    - Target
    - Sender
    - Created
    - Read reason
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Mention a participant in a message

## Trigger

The person includes another participant’s username while posting a message.

## Outcome

The recipient gets an Unread notification linked to that exact discussion item.

## Edge cases

- Self mentions and email-address text do not produce notifications.
- Editing a message notifies only newly added recipients.
- Mentioning a recipient again after removing their mention refreshes the existing notification as unread.
