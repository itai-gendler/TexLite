---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses a folder and name, or drags the item onto a folder
  kind: actor
  entities:
  - entity: folder
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite changes the file path and follows comment targets
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Path
    - Language
  - entity: comment
    effect: changes
    facts:
    - File path
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Move or rename a source file

## Trigger

The person chooses Move or rename for a source file, or drags it onto another folder.

## Outcome

The path changes, open workspaces follow it, and affected comment paths follow. A configured root or latexmkrc continues to refer to the same moved file.

## Edge cases

- An occupied destination is refused.
- The configured main document must keep a .tex extension.
