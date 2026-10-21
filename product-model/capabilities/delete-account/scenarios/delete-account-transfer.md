---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator confirms removal and transfer
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite transfers ownership
  kind: product
  entities:
  - entity: project
    effect: changes
    facts:
    - Owner
    - Modified
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite removes the account
  kind: product
  entities:
  - entity: account
    effect: removes
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Delete an account and keep its projects

## Trigger

An administrator confirms deleting another account with the default keep-projects choice.

## Outcome

Owned projects transfer to the acting administrator. Personal library, tags, memberships and sessions are removed. Existing discussions retain Deleted User attribution.
