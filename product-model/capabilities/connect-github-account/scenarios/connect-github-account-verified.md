---
kind: primary
routes:
  web: Browser
steps:
- text: The person supplies the token
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::github
  actor: user
- text: TexLite saves the GitHub account connection
  kind: product
  entities:
  - entity: github-account
    effect: creates
    facts:
    - Login
    - Token
    - Configured
  contexts:
    web:
      place: web::writing::github
  actor: user
---

# Connect a verified GitHub account

## Trigger

The person supplies a personal token.

## Outcome

TexLite stores the connection and shows the verified GitHub login.
