---
kind: edge
routes:
  web: Browser
steps:
- text: The person requests compilation
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports that the source could not be saved consistently and asks to try again
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Retry when the source cannot be saved first

## Trigger

The latest edits cannot be saved before the compile takes its copy of the source.

## Outcome

Nothing is compiled; the person is asked to try again in a moment rather than getting a PDF of older text.
