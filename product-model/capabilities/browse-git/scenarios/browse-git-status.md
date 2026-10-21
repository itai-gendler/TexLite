---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens Git
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite reads Git repository and Git commit information
  kind: product
  entities:
  - entity: git-repository
    effect: reads
    facts:
    - Remote
    - Name
    - Visibility
    - Branch
    - Default branch
    - Changes
    - Pushed
  - entity: git-commit
    effect: reads
    facts:
    - Revision
    - Message
    - Author
    - Time
    - Difference
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Inspect Git work and revisions

## Trigger

The person opens Git for the project.

## Outcome

TexLite shows repository status, available commits, and selected differences, including an explicit truncation indication for large diffs.
