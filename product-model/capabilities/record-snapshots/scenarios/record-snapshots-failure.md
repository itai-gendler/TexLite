---
kind: unattended
routes:
  web: Browser
steps:
- text: A source change has been saved
  kind: condition
  unattended: true
  entities: []
  contexts:
    web:
      place: web::writing::history
- text: TexLite warns that some history could not be saved
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::history
---

# Report incomplete history recording

## Trigger

The source is saved, but recording its snapshot or selection history fails.

## Outcome

The source stays saved and the workspace warns that some history could not be saved. Recent failures are retried automatically, so older history may be incomplete.
