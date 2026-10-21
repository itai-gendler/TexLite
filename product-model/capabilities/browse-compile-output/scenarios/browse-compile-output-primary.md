---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens the compile output for the selected main document
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite shows the latest compile job for that main document
  kind: product
  entities:
  - entity: compile-job
    effect: reads
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
---

# Browse compile output

## Trigger

The person wants to see how the last compile went.

## Outcome

The person sees the compile status, the log, structured warnings and errors, the retained PDF and the generated files.
