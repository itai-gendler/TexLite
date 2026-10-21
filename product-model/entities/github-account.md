---
references:
- kind: code
  role: implementation
  target: src/server/git.ts#ProjectGitService
- kind: code
  role: implementation
  target: src/client/GitHubAccountDialog.tsx
---

# GitHub account

The personal connection used when its account owns a backed-up project.

## Information kept

- **Login** — The verified GitHub username.
- **Token** — The supplied personal credential.
- **Configured** — Whether a credential is saved.
