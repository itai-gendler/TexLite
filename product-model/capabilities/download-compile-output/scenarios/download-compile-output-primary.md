---
kind: primary
routes:
  web: Browser
steps:
- text: The person downloads the PDF or another generated output
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite returns the compile job's retained output
  kind: product
  entities:
  - entity: compile-job
    effect: reads
    facts:
    - Root
    - PDF
    - Artifacts
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Download compile output

## Trigger

The person wants the compiled PDF, or another generated file such as the log, outside TexLite.

## Outcome

The selected output is downloaded. A removed artifact reports unavailable; supported small text artifacts can also be previewed.
