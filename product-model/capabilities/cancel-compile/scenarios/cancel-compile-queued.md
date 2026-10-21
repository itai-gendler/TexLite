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
- text: TexLite cancels the compile job
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Queued
    to: Cancelled
    facts:
    - Finished
    - Log
    - Cache available
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Cancel a queued compile

## Trigger

The person chooses Cancel compile for the selected main document.

## Outcome

The job is cancelled and pending follow-up requests are discarded. The previous PDF remains; a cancelled running job’s partial cache is cleared.
