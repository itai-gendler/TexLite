---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms a retained path
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite restores the selected file and adjusts its comment anchors
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Files
    - Fingerprint
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
  - entity: comment
    effect: changes
    facts:
    - Anchor
    - Quote
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Restore one retained file

## Trigger

The person chooses Restore file for one file in the snapshot.

## Outcome

Only that path is restored, including attachment bytes where applicable; shared compiler settings remain as they were.
