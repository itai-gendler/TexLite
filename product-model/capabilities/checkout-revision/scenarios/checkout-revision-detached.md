---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms the revision
  kind: actor
  entities:
  - entity: git-commit
    effect: reads
    facts:
    - Revision
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite checks out source and changes the Git repository position
  kind: product
  entities:
  - entity: git-repository
    effect: changes
    facts:
    - Branch
    - Changes
  - entity: file
    effect: changes
    facts:
    - Path
    - Content
    - Size
    - Language
    as: retained-file
  - entity: attachment
    effect: changes
    facts:
    - Path
    - Content
    - Size
    - Preview type
    as: retained-attachment
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
      place: web::writing::git
  actor: user
---

# Inspect a historical revision

## Trigger

The owner chooses Checkout this version on a commit in the Git history.

## Outcome

The project's files become those of that commit, detached from the branch; comments are re-anchored and open workspaces reload.

## Edge cases

- Normal checkout keeps local changes where possible and refuses conflicts.
- The current source is saved and a safety checkpoint snapshot is taken first.
- Files in both trees take the revision's contents, files only in the revision come back with their folders, and files the revision does not have are removed.
