---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters a commit message
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite commits the current changes as a Git commit with that message
  kind: product
  entities:
  - entity: git-commit
    effect: creates
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

# Commit project

## Trigger

The owner wants to record the current state in Git.

## Outcome

The commit records all current working changes using the owner’s identity. Empty messages, no changes, and detached revisions are refused.
