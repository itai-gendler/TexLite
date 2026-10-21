---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator sets a temporary password, or generates one
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite saves the temporary password and ends the person's login sessions and collaboration sessions
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Password
    - Password change required
  - entity: login-session
    effect: removes
  - entity: collaboration-session
    effect: removes
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Reset password

## Trigger

A teammate has forgotten their password.

## Outcome

The person is signed out everywhere and signs in with the temporary password, then chooses a new one.
