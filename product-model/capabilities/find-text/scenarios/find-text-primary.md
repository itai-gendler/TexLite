---
kind: primary
routes:
  web: Browser
steps:
- text: The person searches the open file, optionally matching case, whole words or a regular expression
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite highlights the matches in the file and counts them
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Find text

## Trigger

The person looks for text in the file they are editing.

## Outcome

The current document shows matches and their count; invalid expressions and no matches are reported.
