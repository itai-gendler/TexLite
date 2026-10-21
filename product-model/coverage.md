---
scope: Browser writing, review, compilation, snapshots, personal organization and citations, Git backup, and
  account administration.
method: Static tracing of browser surfaces, route handlers, services, persistence, configuration and selected
  tests at the source commit.
covered:
- description: Browser writing and review surfaces with their source and collaboration services.
  paths:
  - src/client/pages/
  - src/client/workspace/
  - src/client/LatexEditor.tsx
  - src/client/collaboration.ts
  - src/server/routes/
  - src/server/collaboration.ts
  - src/server/projectMutations.ts
  - src/server/projects.ts
  - src/server/files.ts
  - src/server/anchors.ts
  - src/shared/sourceCommentAnchors.ts
- description: Compile coordination, retained output and source navigation.
  paths:
  - src/server/compiler.ts
  - src/server/compileArtifacts.ts
  - src/server/synctex.ts
  - src/server/latexRoot.ts
  - src/server/projectOutline.ts
  - src/server/projectReferences.ts
- description: Recovery snapshots, passage history, comment mentions and Git work.
  paths:
  - src/server/history.ts
  - src/server/historyRetention.ts
  - src/server/editHistory.ts
  - src/server/commentMentions.ts
  - src/server/git.ts
  - src/client/HistoryDialog.tsx
  - src/client/SelectionHistoryDialog.tsx
  - src/client/GitDialog.tsx
- description: Writing assistance, word counts, formatting, PDF preview, ZIP import and export, and account security
    helpers.
  paths:
  - src/client/latexFormatter.ts
  - src/client/spellCheck.ts
  - src/client/chktex.ts
  - src/client/PdfPreview.tsx
  - src/client/GitHubAccountDialog.tsx
  - src/server/harper.ts
  - src/server/chktex.ts
  - src/server/texcount.ts
  - src/server/zip.ts
  - src/server/archive.ts
  - src/server/security.ts
- description: Personal citation and editor-setting behavior, backed by account and project data.
  paths:
  - src/client/CitationLibraryDialog.tsx
  - src/client/CitationTagManagementDialog.tsx
  - src/client/citationLibrary.ts
  - src/client/editorPreferences.ts
  - src/server/db.ts
  - src/server/auth.ts
  - src/server/config.ts
exclusions:
- description: Packaging, parser generation, CI and tests are supporting implementation rather than product
    surfaces.
  paths:
  - scripts/
  - .github/
  - tests/
  - src/client/latex/
  - src/client/bibtex/
- description: Marketing site and decorative presentation are outside the product behavior model.
  paths:
  - website/
  - src/client/styles.css
  - src/client/siteTheme.css
  - src/client/public/
unmapped:
- description: Host CLI provisioning, runtime lifecycle and diagnosis are deferred to keep the model focused
    on shared writing.
  paths:
  - src/server/cli.ts
  - src/server/environment.ts
  - src/server/service.ts
  - src/server/pm2.ts
  - src/server/logRotation.ts
  - src/server/runtimePaths.ts
  - src/server/instanceLock.ts
- description: Administrator operational metrics and release reminders are peripheral to the writing workflows.
  paths:
  - src/server/updates.ts
  - src/server/metrics.ts
  - src/server/resourceMetrics.ts
  - src/server/cpuMetrics.ts
  - src/client/SystemMetricsDialog.tsx
  - src/client/UpdateNotification.tsx
- description: Browser language and visual appearance preference controls are deferred; supported interface
    languages remain declared.
  paths:
  - src/client/LanguageSwitcher.tsx
  - src/client/i18n.ts
  - src/client/theme.ts
  - src/client/ThemeSwitcher.tsx
- description: Account disabling and display-name changes in the user administration routes, which the browser does
    not offer.
  paths:
  - src/server/routes/users.ts
- description: The hand-off from signing in to a required password change, kept as two capabilities without a
    journey because the person signs in partway through it.
  paths:
  - src/client/App.tsx
  - src/client/pages/AuthPages.tsx
limitations: []
---

# Coverage
