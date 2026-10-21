---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms restoring the snapshot they inspected
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Files
    - Compiler settings
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite restores the project's source files and compiler settings from the snapshot
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Fingerprint
    - Files
    - Compiler settings
  - entity: file
    effect: changes
    facts:
    - Content
    - Path
    - Size
    - Language
    as: retained-file
  - entity: attachment
    effect: changes
    facts:
    - Content
    - Path
    - Size
    - Preview type
    as: retained-attachment
  - entity: project
    effect: changes
    facts:
    - Main document
    - Engine
    - Latexmkrc
    - ChkTeX enabled
    - Modified
  - entity: comment
    effect: changes
    facts:
    - Anchor
    - Quote
  - entity: file
    as: restored-file
    effect: creates
    facts:
    - Path
    - Content
    - Language
    - Size
  - entity: file
    as: removed-file
    effect: removes
  - entity: attachment
    as: restored-attachment
    effect: creates
    facts:
    - Path
    - Content
    - Preview type
    - Size
  - entity: attachment
    as: removed-attachment
    effect: removes
  - entity: folder
    as: restored-folder
    effect: creates
    facts:
    - Path
  - entity: folder
    as: removed-folder
    effect: removes
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Restore a whole snapshot

## Trigger

The person chooses Restore project on a snapshot and confirms.

## Outcome

The project's files and compiler settings become those of the snapshot, comments are re-anchored, and open workspaces reload the restored source.

## Edge cases

- The current source is saved and a safety checkpoint snapshot is taken first; when nothing changed since the latest snapshot, no extra one is added.
- Files in both take the snapshot's contents, files only in the snapshot come back with their folders, and files the snapshot does not have are removed. Empty folders are not part of a snapshot.
