---
id: texlite
summary: Self-hosted collaborative LaTeX writing for small, trusted research teams.
category: collaborative-writing
tags:
- latex
- collaboration
- self-hosted
authors:
- name: SWUFE-DB-Group
license: AGPL-3.0-only
languages:
- en
- zh
limitations:
- TexLite serves small, trusted teams on a single host with one application instance per data directory.
- Accounts are provisioned by administrators; public registration is unavailable.
- Compilation uses the host LaTeX distribution; TexLite does not install or update TeX packages.
- Citation libraries belong privately to individual users.
references:
- kind: doc
  role: intent
  target: README.md
- kind: doc
  role: context
  target: DESIGN.md
- kind: code
  role: implementation
  target: src/server/config.ts
- kind: code
  role: implementation
  target: src/server/routes/auth.ts#registerAuthRoutes
- kind: code
  role: implementation
  target: src/server/routes/citations.ts#registerCitationRoutes
---

# TexLite

TexLite is a self-hosted browser workspace for teams to write LaTeX together, review source comments, compile documents, and recover earlier work. Projects combine source files and attachments with sharing, history, retained PDFs, and optional GitHub backup.

## Intent

A lightweight, self-hosted LaTeX writing environment for small, trusted research teams: they use their existing LaTeX distribution, with no heavyweight service stack. The team owns the writing environment, keeping sources, history and compiled output in one local data directory, and controls capacity, TeX updates, data location and the collaboration workflow. TexLite is built for shared browser writing, not as a replacement for a personal IDE.
