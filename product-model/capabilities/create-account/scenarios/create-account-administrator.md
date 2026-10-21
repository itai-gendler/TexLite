---
kind: alternate
routes:
  web: Browser
steps:
- text: The administrator supplies the new identity
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite creates the account and its administrator role
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
  - entity: administrator
    effect: creates
    facts: []
    with: account
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Create an administrator account

## Trigger

An administrator chooses the administrator role for a new account.

## Outcome

The new account holds the Administrator role and can create projects.
