# Build statistics — Carbon rework

Before/after review for the Build Management statistics component, refreshed on 26 October 2026. The captures render the actual React/Carbon components with identical example builds.

## Scope

- Before: current public `main`, `3b68396284e7f65ab51f405a3838639d91b97b26`.
- After: signed commit `30f2b85d83f66908c9cd9d5c2aa8861f4b8ec17c` on `fix/build-statistics-carbon`, directly on that main commit.
- Exactly three changed files: `src/components/BuildStatistics.jsx`, `src/styles/build-statistics.scss` and the statistics styles/import in `src/index.scss`.
- The already merged shared headings, other pages, API services, auth, IPC, main process and dependency manifests are unchanged. This is independent of Analytics PR #104 and the multi-key work.
- Four Carbon metric tiles and a compact stage table replace the custom icon cards and status bars. Only actual creator IDs count toward the unique-creator total; unavailable creator data is disclosed.
- Completion still means acknowledged contract download. Finalized builds remain active until downloaded, and table search does not change the overview scope.

## Validation

`npm ci`, `npm run build` and `git diff --check` passed using the current lockfile (Carbon React 1.119.0, Electron 45.0.0). Browser checks covered counts, shares, creator deduplication, legacy/unknown stages, empty/loading states, refresh, table search, build detail selection, create-dialog cancellation and viewer permissions. Eight layout/theme cases passed at 390, 768, 900 and 1600 px in white/g100. Both capture environments loaded IBM Plex Sans regular and semibold successfully. [Browser checks](browser-results.json) · [Layout checks](layout-results.json) · [Isolation verification](scope-verification.json).

The repository has no configured test runner or lint script. Verification used an external browser harness with mocked read-only API responses; no central backend accounts, builds or signing keys were changed. These checks do not claim a new end-to-end backend test.

## Capture notes

Desktop viewport: 1600 × 1100; narrow window: 390 × 1100. Only the full-page capture expands the app content scroll area equally before and after to show both build lists. Mixed-stage, empty and loading examples render the actual component directly: Build Management currently mounts statistics only when loading has finished and builds exist. Percentages are rounded independently. The narrow-window stage table scrolls horizontally.

Review images and validation notes live on a separate documentation branch and are not part of the application change.

## Comparisons

### Build overview — desktop

![Before and after — Build overview — desktop](comparisons/01-overview.png)

[Before](before/01-overview.png) · [After](after/01-overview.png) · [Full comparison](comparisons/01-overview.png)

### Build overview — dark theme

![Before and after — Build overview — dark theme](comparisons/02-dark-overview.png)

[Before](before/02-dark-overview.png) · [After](after/02-dark-overview.png) · [Full comparison](comparisons/02-dark-overview.png)

### Build Management — full page

![Before and after — Build Management — full page](comparisons/03-page-context.png)

[Before](before/03-page-context.png) · [After](after/03-page-context.png) · [Full comparison](comparisons/03-page-context.png)

### Workflow, legacy and unknown stages

![Before and after — Workflow, legacy and unknown stages](comparisons/04-all-stages.png)

[Before](before/04-all-stages.png) · [After](after/04-all-stages.png) · [Full comparison](comparisons/04-all-stages.png)

### Build overview — narrow window

![Before and after — Build overview — narrow window](comparisons/05-mobile.png)

[Before](before/05-mobile.png) · [After](after/05-mobile.png) · [Full comparison](comparisons/05-mobile.png)

### Build overview — empty state

![Before and after — Build overview — empty state](comparisons/06-empty.png)

[Before](before/06-empty.png) · [After](after/06-empty.png) · [Full comparison](comparisons/06-empty.png)

### Build overview — loading state

![Before and after — Build overview — loading state](comparisons/07-loading.png)

[Before](before/07-loading.png) · [After](after/07-loading.png) · [Full comparison](comparisons/07-loading.png)

