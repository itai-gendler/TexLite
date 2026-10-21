---
entities:
- entity: github-account
  shows:
  - Login
  - Configured
  collects:
  - Token
references:
- kind: code
  role: implementation
  target: src/client/GitHubAccountDialog.tsx
---

# GitHub account

A person's GitHub connection, reached from their account menu, where they save, replace or remove the token used for their projects' backups.
