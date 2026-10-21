---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Remove token
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::github
  actor: user
- text: TexLite removes the GitHub account connection
  kind: product
  entities:
  - entity: github-account
    effect: removes
  contexts:
    web:
      place: web::writing::github
  actor: user
---

# Disconnect GitHub account

## Trigger

The person no longer wants TexLite to use their GitHub token.

## Outcome

The token is gone; pushes for the projects this person owns need a new connection.
