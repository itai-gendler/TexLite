---
relations:
- entity: project
  verb: owns
  cardinality: one-to-many
- entity: membership
  verb: holds
  cardinality: one-to-many
- entity: project-organization
  verb: keeps
  cardinality: one-to-many
- entity: project-tag
  verb: owns
  cardinality: one-to-many
- entity: citation
  verb: owns
  cardinality: one-to-many
- entity: citation-tag
  verb: owns
  cardinality: one-to-many
- entity: login-session
  verb: holds
  cardinality: one-to-many
- entity: collaboration-session
  verb: holds
  cardinality: one-to-many
- entity: comment
  verb: authors
  cardinality: one-to-many
- entity: reply
  verb: authors
  cardinality: one-to-many
- entity: mention
  verb: receives
  cardinality: one-to-many
- entity: editor-preferences
  verb: keeps
  cardinality: one-to-many
- entity: github-account
  verb: connects
  cardinality: one-to-one
- entity: user
  verb: uses
  cardinality: one-to-one
- entity: administrator
  verb: uses
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: src/server/db.ts
- kind: code
  role: implementation
  target: src/server/auth.ts
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
---

# Account

The identity and personal information shared by a person’s user or administrator role.

## Information kept

- **Username** — The unique sign-in name.
- **Display name** — The name shown to teammates.
- **Password** — The current sign-in secret, collected when set or changed.
- **Password change required** — Whether the person must choose a new password after an administrator reset it.
- **Project creation allowed** — Whether a user may create, import, or duplicate projects.
- **Created** — When the account was added.
