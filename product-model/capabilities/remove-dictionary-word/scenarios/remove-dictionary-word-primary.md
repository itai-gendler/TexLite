---
kind: primary
routes:
  web: Browser
steps:
- text: The person removes a word from the project dictionary
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite removes the dictionary word
  kind: product
  entities:
  - entity: dictionary-word
    effect: removes
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Remove dictionary word

## Trigger

A word was added to the dictionary by mistake.

## Outcome

Open workspaces refresh their writing checks, so the word is reported again where it is misspelled.
