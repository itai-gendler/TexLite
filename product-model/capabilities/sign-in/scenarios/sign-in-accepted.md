---
kind: primary
routes:
  web: Browser
steps:
- text: The visitor supplies credentials
  kind: actor
  entities: []
  contexts:
    web:
      place: web::sign-in::login
  actor: visitor
- text: TexLite starts a login session
  kind: product
  entities:
  - entity: login-session
    effect: creates
    facts:
    - Started
    - Expires
  contexts:
    web:
      place: web::sign-in::login
  actor: visitor
---

# Sign in with valid credentials

## Trigger

A visitor submits a username and password.

## Outcome

A session starts. The browser opens the requested destination or, after an administrator password reset, requires Change password.
