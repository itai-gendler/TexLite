---
kind: alternate
routes:
  web: Browser
steps:
- text: The person supplies the selection
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the project configuration selection
  kind: product
  entities:
  - entity: project
    effect: changes
    facts:
    - Latexmkrc
    - Modified
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Select project latexmkrc

## Trigger

The person chooses an existing project latexmkrc when that option is available.

## Outcome

Later compiles use the selected configuration file; clearing the choice returns to ordinary project compiler settings.
