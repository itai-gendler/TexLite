---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Sign out
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite ends the login session
  kind: product
  entities:
  - entity: login-session
    effect: removes
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Sign out

## Trigger

The person is done working.

## Outcome

The session ends and the browser returns to sign-in; the person's sessions in other browsers stay.
