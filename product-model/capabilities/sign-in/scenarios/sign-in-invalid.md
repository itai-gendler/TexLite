---
kind: validation
routes:
  web: Browser
steps:
- text: The visitor submits credentials
  kind: actor
  entities: []
  contexts:
    web:
      place: web::sign-in::login
  actor: visitor
- text: TexLite reports that sign-in failed
  kind: product
  entities: []
  contexts:
    web:
      place: web::sign-in::login
  actor: visitor
---

# Reject invalid credentials

## Trigger

The credentials do not identify an active account.

## Outcome

Sign-in fails and the person can correct the credentials.

## Edge cases

- After repeated failures, further attempts for that username from the same address are refused for a while.
