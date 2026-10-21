---
kind: primary
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
- text: TexLite creates a queued compile job
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
- text: TexLite runs the compile job against saved file content
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Queued
    to: Running
    facts:
    - Source freshness
    - Cache available
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
    - Size
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite publishes the compile job result
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    from: Running
    to: Succeeded
    facts:
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

# Compile and publish a successful result

## Trigger

The person requests a compile for the selected main document.

## Outcome

The successful PDF and generated artifacts become the retained result for that root, with log and structured diagnostics.

## Edge cases

- An invalid or changed main document is rejected before compilation proceeds.
- Global capacity limits queue work; different roots are coordinated independently.

## Decision points

### Format before compile

Does the saved editing preference request formatting?

- Enabled and eligible source → TexLite attempts formatting before saving and compiling; a formatting failure is reported and compilation continues.
- Disabled or ineligible source → TexLite saves and compiles directly.
