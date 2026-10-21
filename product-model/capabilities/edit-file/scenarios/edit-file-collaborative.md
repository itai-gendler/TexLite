---
kind: primary
routes:
  web: Browser
steps:
- text: The person edits file content
  kind: actor
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the file and remaps comment anchors
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
  - entity: comment
    effect: changes
    facts:
    - Anchor
    - Quote
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Edit and save shared source

## Trigger

A person types in a synchronized source file.

## Outcome

The merged source is visible to collaborators, saved status follows successful persistence, and comments follow the edited passage.

## Edge cases

- Undo/redo uses the active file’s editing history and survives editor-tab switches.
- Completion includes local unsaved definitions as well as project definitions and bibliography keys.
