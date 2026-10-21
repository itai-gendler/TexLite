---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters replacement text and chooses Replace or Replace all
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite replaces the next match, or every match, in the open file
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Replace text

## Trigger

The person wants to change repeated text in the file they are editing.

## Outcome

The replacement lands in the shared source like any other edit; other files are not searched.
