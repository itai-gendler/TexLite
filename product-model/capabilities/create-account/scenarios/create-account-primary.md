---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator supplies identity and initial credentials
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite creates the account with the User role
  kind: product
  entities:
  - entity: account
    effect: creates
    facts:
    - Username
    - Display name
    - Password
    - Password change required
    - Project creation allowed
    - Created
  - entity: user
    effect: creates
    facts: []
    with: account
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Create account

## Trigger

An administrator adds a teammate in Users.

## Outcome

A new user account is ready to sign in. Project creation starts off unless explicitly allowed.
