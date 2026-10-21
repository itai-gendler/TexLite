---
references:
- kind: code
  role: implementation
  target: src/client/editorPreferences.ts
- kind: code
  role: implementation
  target: src/client/workspace/ProjectSettings.tsx
---

# Editor preferences

Browser-local writing preferences for one person and project.

## Information kept

- **Vim mode** — Whether Vim editing is enabled; initially off.
- **Spelling assistance** — Whether spelling and grammar assistance is requested; initially on.
- **Format before compile** — Whether the active eligible source is formatted before compiling; initially off.
- **Formatter options** — The tex-fmt options used when formatting; initially wrapping is disabled.
- **Open files in tabs** — Whether eligible text files are kept in editor tabs; initially off.
- **Math preview** — Whether hovering offers a math preview; initially off.
