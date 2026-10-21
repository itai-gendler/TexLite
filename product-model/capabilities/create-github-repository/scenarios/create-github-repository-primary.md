---
kind: primary
routes:
  web: Browser
steps:
- text: The owner enters a repository name and keeps or clears Private
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::git
  actor: user
- text: TexLite creates the repository on GitHub and starts the local Git repository
  kind: product
  entities:
  - entity: git-repository
    effect: creates
    facts:
    - Remote
    - Name
    - Visibility
    - Branch
    - Default branch
    - Changes
    - Pushed
  contexts:
    web:
      place: web::writing::git
  actor: user
---

# Create GitHub repository

## Trigger

The owner sets up a GitHub backup for the project.

## Outcome

The repository destination is saved for the project. An already configured remote is not replaced.
