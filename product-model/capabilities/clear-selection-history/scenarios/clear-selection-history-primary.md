---
kind: primary
routes:
  web: Browser
steps:
- text: The owner confirms Clear project edit history
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite saves pending edits and clears the project's selection history
  kind: product
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: selection-history
    effect: removes
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Clear selection history

## Trigger

The owner wants to free the edit history's storage.

## Outcome

Passage attribution starts anew with future edits. Snapshots and the current source stay.
