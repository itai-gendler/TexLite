---
kind: primary
routes:
  web: Browser
steps:
- text: The owner picks a teammate and Read only or Read & write
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite adds the membership
  kind: product
  entities:
  - entity: membership
    effect: creates
    facts:
    - Role
    - Member
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Share project

## Trigger

The owner wants a teammate to review or edit the project.

## Outcome

The project appears in the teammate's Projects with the chosen access.
