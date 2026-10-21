---
kind: primary
routes:
  web: Browser
steps:
- text: The person adds a word in the project settings
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the dictionary word for the project
  kind: product
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: dictionary-word
    effect: creates
    facts:
    - Word
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Add dictionary word

## Trigger

A correctly spelled word, such as a name or a term, is reported as a spelling issue.

## Outcome

The word is in the project dictionary, and open workspaces refresh their writing checks so it is no longer reported.
