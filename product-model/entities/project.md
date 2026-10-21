---
domain: projects
relations:
- entity: membership
  verb: contains
  cardinality: one-to-many
- entity: project-organization
  verb: contains
  cardinality: one-to-many
- entity: file
  verb: contains
  cardinality: one-to-many
- entity: attachment
  verb: contains
  cardinality: one-to-many
- entity: folder
  verb: contains
  cardinality: one-to-many
- entity: collaboration-session
  verb: contains
  cardinality: one-to-many
- entity: comment
  verb: contains
  cardinality: one-to-many
- entity: mention
  verb: contains
  cardinality: one-to-many
- entity: snapshot
  verb: contains
  cardinality: one-to-many
- entity: selection-history
  verb: contains
  cardinality: one-to-many
- entity: compile-job
  verb: contains
  cardinality: one-to-many
- entity: dictionary-word
  verb: contains
  cardinality: one-to-many
- entity: editor-preferences
  verb: contains
  cardinality: one-to-many
- entity: git-repository
  verb: keeps
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: src/server/routes/projects.ts#registerProjectCatalogRoutes
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
---

# Project

A shared writing project with its own source tree and compiler defaults.

## Information kept

- **Name** — The shared project name.
- **Icon** — The owner-selected project symbol.
- **Owner** — The account responsible for sharing and project administration.
- **Main document** — The default root document.
- **Engine** — One of the engines allowed by the deployment.
- **Latexmkrc** — The selected project configuration file, or none.
- **ChkTeX enabled** — Whether optional LaTeX writing diagnostics are requested.
- **Modified** — Latest change time and changing person.
- **Active sessions** — The number of live or admitted collaboration sessions.
- **Created** — When the project was created.
