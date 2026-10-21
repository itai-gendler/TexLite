---
references:
- kind: code
  role: implementation
  target: src/server/routes/auth.ts#registerAuthRoutes
- kind: code
  role: implementation
  target: src/server/auth.ts
---

# Login session

A signed-in browser session with a fixed lifetime.

## Information kept

- **Started** — When sign-in succeeded.
- **Expires** — When another sign-in will be needed.
