---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator confirms the selected role
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite replaces the account's User role with Administrator
  kind: product
  entities:
  - entity: account
    effect: reads
    facts: []
  - entity: user
    effect: removes
  - entity: administrator
    effect: creates
    facts: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Make an account administrator

## Trigger

An administrator changes a User's role to Administrator in Users and confirms.

## Outcome

The selected person gains the Administrator role.
