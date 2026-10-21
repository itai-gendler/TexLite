---
kind: primary
routes:
  web: Browser
steps:
- text: The administrator searches by username or display name, or turns the page
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite lists the matching accounts, twenty per page
  kind: product
  entities:
  - entity: account
    effect: reads
    facts:
    - Username
    - Display name
    - Password
    - Password change required
    - Project creation allowed
    - Created
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Browse accounts

## Trigger

An administrator opens Users.

## Outcome

Each account shows its display name, username, role, project-creation permission and number of owned projects.
