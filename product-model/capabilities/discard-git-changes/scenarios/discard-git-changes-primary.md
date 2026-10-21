---
kind: primary
routes:
  web: Browser
steps:
- text: The owner confirms Discard changes
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite restores the tracked files to the current Git commit and re-anchors comments
  kind: product
  entities:
  - entity: git-repository
    effect: changes
    facts:
    - Changes
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
    as: modified-file
  - entity: attachment
    effect: changes
    facts:
    - Content
    - Size
    as: modified-attachment
  - entity: comment
    effect: changes
    facts:
    - Anchor
    - Quote
  - entity: git-commit
    effect: reads
    facts:
    - Revision
  - entity: file
    as: restored-file
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Language
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Discard Git changes

## Trigger

The owner wants to drop the uncommitted changes to files Git tracks.

## Outcome

After the current source is saved and a safety checkpoint snapshot is taken, changes to tracked files are discarded and comments are re-anchored; untracked files stay.

A deleted tracked file comes back, and modified tracked files return to their committed contents.
