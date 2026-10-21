---
kind: alternate
routes:
  web: Browser
steps:
- text: The administrator confirms the change
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite changes the acting role
  kind: product
  entities:
  - entity: administrator
    effect: removes
  - entity: user
    effect: creates
    facts: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Make an administrator a User

## Trigger

An administrator confirms changing another administrator to User.

## Outcome

The selected person now holds the User role.
