---
kind: primary
routes:
  web: Browser
steps:
- text: The person picks a suggestion for a reported issue
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite replaces the issue in the file with the suggestion
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

# Apply writing suggestion

## Trigger

The person right-clicks a spelling or grammar issue and picks one of its suggestions.

## Outcome

The flagged text is replaced in the shared source and saved like any other edit.
