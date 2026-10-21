---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses the comparison
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite compares the file in the snapshot with the chosen side
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Files
    - Changed paths
    - Fingerprint
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Compare retained text

## Trigger

The person picks a snapshot and one of its text files, and compares it with the previous snapshot or the current source.

## Outcome

The historical and comparison text show additions, changes, or deletion.

## Edge cases

- An attachment remains recoverable but has no text diff.
- Invalid or oversized text shows preview unavailable.
