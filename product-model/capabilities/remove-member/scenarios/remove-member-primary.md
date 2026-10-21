---
kind: primary
routes:
  web: Browser
steps:
- text: The owner removes a member in Share
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite removes the membership and ends the member's collaboration sessions in the project
  kind: product
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: membership
    effect: removes
  - entity: collaboration-session
    effect: removes
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Remove member

## Trigger

The owner stops sharing the project with someone.

## Outcome

The person loses access at once; their open workspaces are told the project is no longer shared with them.
