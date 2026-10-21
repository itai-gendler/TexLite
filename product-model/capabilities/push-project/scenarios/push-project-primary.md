---
kind: primary
routes:
  web: Browser
steps:
- text: The owner chooses Push
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite pushes the Git repository's branch to GitHub with the owner's GitHub token
  kind: product
  entities:
  - entity: git-repository
    effect: changes
    facts:
    - Pushed
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Push project

## Trigger

The owner has commits that are not yet on GitHub.

## Outcome

The remote receives committed changes. A missing credential, destination, commit, or current branch prevents the push.
