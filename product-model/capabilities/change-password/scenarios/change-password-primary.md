---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters their current password and a new one twice
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::password
  actor: user
- text: TexLite checks the current password and saves the new one on the account
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Password
    - Password change required
  - entity: login-session
    effect: removes
  contexts:
    web:
      place: web::writing::password
  actor: user
---

# Change password

## Trigger

The person wants a new password, or must choose one after an administrator reset it.

## Outcome

The password is changed, the current session continues, and other login sessions end. A required change returns the person to the intended writing destination.
