---
references:
- kind: code
  role: implementation
  target: src/server/routes/compile.ts#registerCompileRoutes
- kind: code
  role: implementation
  target: src/server/compiler.ts
- kind: code
  role: implementation
  target: src/client/workspace/useProjectCompilation.ts
---

# Compile job

A request to compile one project root and its resulting diagnostics and retained output.

## Information kept

- **Root** — The selected main document for this job.
- **Requested by** — The person initiating the compile.
- **Requested** — The request time.
- **Finished** — The completion time, when finished.
- **Log** — The compiler transcript.
- **Diagnostics** — Structured warnings and errors with source locations.
- **PDF** — The successful compiled document and its time and size, when available.
- **Artifacts** — Generated output files available for preview or download.
- **Source freshness** — Whether later edits have made the result older than the current source.
- **Cache available** — Whether incremental work can be reused.

## States

### Queued

The request is waiting to run.

### Running

Compilation is in progress.

### Succeeded

The run produced a PDF.

### Failed

The run ended without a successful result.

### Cancelled

The run was stopped by a participant.
