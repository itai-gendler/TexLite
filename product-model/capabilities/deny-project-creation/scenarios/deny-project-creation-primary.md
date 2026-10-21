---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator confirms disabling creation
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite turns off the account's creation permission
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Project creation allowed
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Deny project creation

## Trigger

An administrator turns off Project creation for a User in Users.

## Outcome

After confirmation, the person can no longer create, import or duplicate projects; projects they already own or share stay available.
