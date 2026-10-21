---
kind: alternate
routes:
  web: Browser
steps:
- text: The person requests compilation again
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite selects the applicable compile job
  kind: product
  entities:
  - entity: compile-job
    effect: reads
    facts:
    - Root
    - Requested
    - Requested by
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Share work and keep the latest pending request

## Trigger

A compile is already active for the same root.

## Outcome

An identical request shares existing work. A newer source generation leaves only the latest follow-up request waiting, and superseded callers receive that result.
