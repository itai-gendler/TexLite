---
kind: edge
routes:
  web: Browser
steps:
- text: The person edits the source
  kind: actor
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports the unsuccessful save
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Report an unsuccessful save

## Trigger

A source write cannot be persisted.

## Outcome

The browser retains an unsaved indication and TexLite retries; operations requiring a successful save do not proceed with older disk contents.

## Edge cases

- Oversized collaborative text is returned to its last saved contents and the rejected path is reported.
