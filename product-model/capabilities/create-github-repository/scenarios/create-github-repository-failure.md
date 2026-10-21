---
kind: edge
routes:
  web: Browser
steps:
- text: The person requests the repository
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite reports the GitHub failure
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Report a repository creation failure

## Trigger

The configured account cannot create the requested repository or GitHub is unavailable.

## Outcome

The panel reports the failure and does not claim a completed backup.
