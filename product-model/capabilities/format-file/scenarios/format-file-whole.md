---
kind: primary
routes:
  web: Browser
steps:
- text: The person requests formatting
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite formats and saves the file
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Format the current source

## Trigger

The person requests formatting for .tex, .cls, .sty, or .bib source.

## Outcome

The formatted text is applied and saved; diagnostic warnings remain available.

## Edge cases

- Concurrent format requests for the same file wait their turn.
