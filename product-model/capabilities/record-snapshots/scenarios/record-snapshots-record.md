---
kind: unattended
routes:
  web: Browser
steps:
- text: A source change has been saved
  kind: condition
  entities: []
  contexts:
    web:
      place: web::writing::history
  unattended: true
- text: TexLite records a snapshot
  kind: product
  entities:
  - entity: snapshot
    effect: creates
    facts:
    - Created
    - Author
    - Reason
    - Label
    - Changed paths
    - Files
    - Compiler settings
    - Fingerprint
    - Storage
  contexts:
    web:
      place: web::writing::history
---

# Retain a saved source change

## Trigger

A change to the project's files is saved.

## Outcome

TexLite keeps the changed file contents with effective compiler settings. Autosaves coalesce within a fixed two-minute window; mixed contributors have no single snapshot author.
