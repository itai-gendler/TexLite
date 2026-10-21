---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses to clear the compile cache
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite clears the compile job's cache for the selected main document
  kind: product
  entities:
  - entity: compile-job
    effect: changes
    facts:
    - Cache available
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Clear compile cache

## Trigger

Compiles behave oddly and the person wants the next one to start from scratch.

## Outcome

The next compile of that main document starts clean; the last successful PDF stays visible meanwhile.
