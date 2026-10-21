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
- text: TexLite recreates the missing path and its parent folder
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Files
    - Fingerprint
  - entity: file
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Language
  - entity: comment
    effect: changes
    facts:
    - Anchor
    - Quote
  - entity: folder
    effect: creates
    facts:
    - Path
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Restore a missing file

## Trigger

The person selects a retained file whose path and parent folder no longer exist in the current tree.

## Outcome

The path and its parent folder are recreated from the snapshot. Other paths and shared compiler settings are unchanged.
