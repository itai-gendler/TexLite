---
kind: unattended
routes:
  web: Browser
steps:
- text: Another automatic save arrives within two minutes of the last
  kind: condition
  entities: []
  contexts:
    web:
      place: web::writing::history
  unattended: true
- text: TexLite updates the latest automatic-save snapshot
  kind: product
  entities:
  - entity: snapshot
    effect: changes
    facts:
    - Files
    - Compiler settings
    - Changed paths
    - Author
    - Fingerprint
  contexts:
    web:
      place: web::writing::history
---

# Coalesce an autosave window

## Trigger

Another saved edit arrives within the current unlabeled autosave window.

## Outcome

The snapshot gains the latest contents and changed paths without pretending one author wrote a mixed-author window.
