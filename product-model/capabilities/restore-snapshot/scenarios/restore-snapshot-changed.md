---
kind: edge
routes:
  web: Browser
steps:
- text: The person confirms the inspected snapshot
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite reports that the snapshot has changed
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Fingerprint
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Reject an unreviewed snapshot change

## Trigger

The snapshot the person inspected was an automatic save that has since been updated.

## Outcome

The restore is refused because the snapshot changed; the person reviews it again before restoring. Nothing is replaced.

## Edge cases

- A snapshot or file that no longer exists is reported as unavailable.
- A single-file restore cannot replace a directory.
