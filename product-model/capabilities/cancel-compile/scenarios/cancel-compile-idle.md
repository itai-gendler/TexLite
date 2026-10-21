---
kind: alternate
routes:
  web: Browser
steps:
- text: The person chooses Cancel compile
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports no active work
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Cancel when no compile is active

## Trigger

The person chooses Cancel compile when no compile of the selected main document is active.

## Outcome

TexLite reports that there was nothing to cancel; nothing changes.
