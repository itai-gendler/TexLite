---
kind: validation
routes:
  web: Browser
steps:
- text: The person supplies the password change
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::password
  actor: user
- text: TexLite reports the invalid input
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::password
  actor: user
---

# Reject an invalid password change

## Trigger

The current password is wrong or the new password is too short.

## Outcome

The password remains unchanged; a confirmation that does not match the new password is refused too.
