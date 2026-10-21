---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator confirms enabling creation
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite turns on the account's creation permission
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

# Allow project creation

## Trigger

An administrator turns on Project creation for a User in Users.

## Outcome

After confirmation, the person can create, import and duplicate projects.
