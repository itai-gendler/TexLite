---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms the branch
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite changes the Git repository position and source
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

# Return to the default branch

## Trigger

The person chooses the default branch.

## Outcome

The working tree returns to that branch and subsequent commits can be made there.

Files in both trees take the revision's contents, files only in the revision come back with their folders, and files the revision does not have are removed.
