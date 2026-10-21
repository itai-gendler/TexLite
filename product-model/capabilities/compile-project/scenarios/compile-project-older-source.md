---
kind: alternate
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
- text: TexLite queues a compile job with a copy of the saved source
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
- text: TexLite runs the compile job on its copy while editing continues
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
- text: The source changes again before the compile finishes
  kind: condition
  actor: user
  entities: []
  contexts:
    web:
      place: web::writing::project
- text: TexLite publishes the compile job's PDF and marks it older than the current source
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Running
    to: Succeeded
    facts:
    - Finished
    - PDF
    - Artifacts
    - Log
    - Diagnostics
    - Source freshness
    - Cache available
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Publish a result while newer edits exist

## Trigger

Someone keeps editing after the compile has taken its copy of the source.

## Outcome

The compile finishes from the copy it took, and its PDF is marked as older than the current source; editing was never blocked.
