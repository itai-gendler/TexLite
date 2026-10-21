---
kind: primary
routes:
  web: Browser
steps:
- text: The owner switches a member between Read only and Read & write
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite changes the membership and updates the member's open collaboration sessions
  kind: product
  entities:
  - entity: membership
    effect: changes
    facts:
    - Role
  - entity: collaboration-session
    effect: changes
    facts:
    - Permission
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Change member permission

## Trigger

The owner wants a reviewer to edit, or an editor only to review.

## Outcome

The member's access changes at once, including in workspaces they already have open.
