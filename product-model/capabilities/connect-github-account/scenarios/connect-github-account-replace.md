---
kind: alternate
routes:
  web: Browser
steps:
- text: The person supplies the replacement token
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::github
  actor: user
- text: TexLite changes the GitHub account connection
  kind: product
  entities:
  - entity: github-account
    effect: changes
    facts:
    - Login
    - Token
    - Configured
  contexts:
    web:
      place: web::writing::github
  actor: user
---

# Replace a GitHub credential

## Trigger

The person saves a new token for an existing connection.

## Outcome

The validated credential and login replace the existing connection.
