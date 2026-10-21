---
kind: primary
routes:
  web: Browser
steps:
- text: The person selects a passage
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite reconstructs selection history
  kind: product
  entities:
  - entity: selection-history
    effect: reads
    facts:
    - File path
    - Contributors
    - Time
    - Operation
    - Passage
    - Boundary
    - Storage
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Inspect a fixed passage

## Trigger

The person selects source and opens its history.

## Outcome

The view keeps that selection fixed and shows reconstructed content, contributors, times, and comparisons across retained windows.

## Edge cases

- Retention, replacement, or missing-chain boundaries stop reconstruction instead of guessing attribution.
- The display reports when more windows exist beyond its limit.
