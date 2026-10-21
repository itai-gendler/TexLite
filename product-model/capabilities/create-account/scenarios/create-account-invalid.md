---
kind: validation
routes:
  web: Browser
steps:
- text: The administrator submits the new identity
  kind: actor
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
- text: TexLite rejects the input
  kind: product
  entities: []
  contexts:
    web:
      place: web::administration::users
  actor: administrator
---

# Reject an invalid new account

## Trigger

The supplied username is invalid or already used, or the password is too short.

## Outcome

No account is added; the form reports the problem.
