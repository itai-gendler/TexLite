---
kind: edge
routes:
  web: Browser
steps:
- text: The person opens Git
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite reports the dependency problem
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Report unavailable Git

## Trigger

The host Git command is unavailable.

## Outcome

The panel reports the missing dependency; normal source editing and compilation remain available.
