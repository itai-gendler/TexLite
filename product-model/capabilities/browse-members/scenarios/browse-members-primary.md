---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens Share for the project
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite lists each membership with its access
  kind: product
  entities:
  - entity: membership
    effect: reads
    facts:
    - Role
    - Member
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Browse members

## Trigger

The person wants to know who else works on the project.

## Outcome

Every member is listed with Read only or Read & write.
