---
kind: primary
routes:
  web: Browser
steps:
- text: The person supplies the changed fields
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the project compiler defaults
  kind: product
  entities:
  - entity: project
    effect: changes
    facts:
    - Name
    - Main document
    - Engine
    - ChkTeX enabled
    - Modified
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Save compiler settings

## Trigger

The person submits changed compiler settings.

## Outcome

The shared settings change and affect later operations. Settings alone do not add a snapshot.

## Edge cases

- A candidate main document must be a real root, with the sole-TeX-file compatibility fallback.
