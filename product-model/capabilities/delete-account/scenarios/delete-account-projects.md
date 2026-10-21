---
kind: alternate
routes:
  web: Browser
steps:
- text: The administrator confirms the deletion choice
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite removes the owned projects and account
  kind: product
  entities:
  - entity: project
    effect: removes
    with: account
  - entity: account
    effect: removes
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Delete an account and its owned projects

## Trigger

An administrator selects the delete-owned-projects choice.

## Outcome

The account and its owned projects, including source and output, are removed.
