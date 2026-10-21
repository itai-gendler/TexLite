---
appliesTo:
- type: entity
  id: comment
  facts:
  - Anchor
  - Quote
references:
- kind: code
  role: implementation
  target: src/server/anchors.ts
- kind: code
  role: implementation
  target: src/shared/sourceCommentAnchors.ts
---

# Comment anchors follow partial source edits and preserve detached quotes

Partial edits update the attached quote. Whole-range replacement or deletion detaches it while preserving its last quote and context; full contextual restoration can reattach it.
