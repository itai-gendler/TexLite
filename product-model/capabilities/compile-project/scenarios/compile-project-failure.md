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
- text: TexLite queues a compile job
  kind: product
  entities:
  - entity: compile-job
    effect: creates
    to: Queued
    facts:
    - Root
    - Requested by
    - Requested
    - Finished
    - Log
    - Diagnostics
    - PDF
    - Artifacts
    - Source freshness
    - Cache available
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite starts the compile job
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Queued
    to: Running
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite records the failed compile job
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Running
    to: Failed
    facts:
    - Finished
    - Log
    - Diagnostics
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Keep the previous PDF after a failed compile

## Trigger

The compiler fails, produces no PDF, or reaches the configured timeout.

## Outcome

The failed result exposes diagnostics and its transcript. The last successful PDF remains available.
