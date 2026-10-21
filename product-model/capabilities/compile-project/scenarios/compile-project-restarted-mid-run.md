---
kind: unattended
routes:
  web: Browser
steps:
- text: The server restarts with unfinished compilation
  kind: condition
  unattended: true
  entities: []
  contexts:
    web:
      place: web::writing::project
- text: TexLite ends the unfinished compile job
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Running
    to: Failed
    facts:
    - Log
    - Finished
  contexts:
    web:
      place: web::writing::project
---

# End a running compile after restart

## Trigger

Startup finds a request that did not finish before restart.

## Outcome

The unfinished request is marked failed. Previously published successful output remains available.
