---
kind: edge
routes:
  web: Browser
steps:
- text: The person requests statistics
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports the tool problem
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Report unavailable statistics

## Trigger

TeXcount is absent or fails.

## Outcome

The statistics request reports unavailable or failed counts; source remains usable.
