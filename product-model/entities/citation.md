---
domain: citation-library
references:
- kind: code
  role: implementation
  target: src/server/routes/citations.ts#registerCitationRoutes
- kind: code
  role: implementation
  target: src/client/CitationLibraryDialog.tsx
---

# Citation

A personally saved BibTeX reference independent of project source.

## Information kept

- **Key** — A case-insensitively unique citation key within the owner’s library.
- **Entry type** — The BibTeX entry type.
- **BibTeX** — The complete stored reference text.
- **Title** — The work title.
- **Authors** — The work authors.
- **Year** — The publication year.
- **Tags** — Personal citation tags assigned to the entry.
- **Revision** — The version last read for concurrent-edit checks.
- **Modified** — The most recent save time.
