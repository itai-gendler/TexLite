---
kind: primary
routes:
  web: Browser
steps:
- text: The person inspects writing assistance
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite checks the source and spelling exceptions
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Content
  - entity: dictionary-word
    effect: reads
    facts:
    - Word
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Inspect writing diagnostics

## Trigger

The person edits eligible source with writing assistance enabled.

## Outcome

TexLite shows available Harper and enabled ChkTeX findings, filtered by the project dictionary.
