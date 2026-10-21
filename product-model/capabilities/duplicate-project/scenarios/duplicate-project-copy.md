---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses the source to copy
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite creates a project copy from a successfully saved source tree
  kind: product
  entities:
  - entity: project
    effect: creates
    facts:
    - Name
    - Icon
    - Owner
    - Main document
    - Engine
    - Latexmkrc
    - ChkTeX enabled
    - Modified
    - Created
    - Active sessions
    as: copy
  - entity: file
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Language
    with: copy
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Duplicate a project after saving live work

## Trigger

A person supplies the copy name.

## Outcome

The catalog gains an owned copy with its own initial history. Sharing, discussions, archive assignments, tags, Git repository, and compiled output are not copied.
