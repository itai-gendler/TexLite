---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters a name for the snapshot
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite saves the label on the snapshot
  kind: product
  entities:
  - entity: snapshot
    effect: changes
    facts:
    - Label
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Label a snapshot

## Trigger

The person marks a state worth keeping, such as a submitted draft.

## Outcome

The snapshot shows its name and is protected from automatic pruning.
