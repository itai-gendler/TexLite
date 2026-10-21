---
entities:
- entity: citation
  shows:
  - Key
  - Entry type
  - BibTeX
  - Title
  - Authors
  - Year
  - Tags
  - Revision
  - Modified
  collects:
  - BibTeX
  - Tags
- entity: citation-tag
  shows:
  - Name
  - Color
references:
- kind: code
  role: implementation
  target: src/client/CitationLibraryDialog.tsx
---

# Citation library

A person's private citation library, opened from Projects or from a .bib file in a project: searching and tagging saved references, and, from a .bib file, saving its entries and importing saved ones into it.
