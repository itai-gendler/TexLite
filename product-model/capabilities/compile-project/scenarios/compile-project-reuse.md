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
- text: TexLite returns the existing compile job result
  kind: product
  entities:
  - entity: compile-job
    effect: reads
    facts:
    - PDF
    - Artifacts
    - Log
    - Diagnostics
    - Root
    - Finished
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Reuse an unchanged successful result

## Trigger

Nothing in the saved source or compiler settings changed since the last successful compile of that main document.

## Outcome

The retained result is reused without another compiler run.
