# User management — before and after

Review images for the combined User Management directory rework and compact-role fix. Before is public `main` at `3b68396284e7f65ab51f405a3838639d91b97b26`. After is `7139f587c1321d7911d07e1f3493049e96000879`, one signed commit directly on that base. This documentation branch contains only review assets; none of these images is part of the code PR.

Actual React/Carbon views use the same 30 deterministic sample accounts with mocked API responses, including an account with all six roles. No real central account data appears in these captures. Desktop captures use 1600 × 1100 and the narrow-window capture uses 390 × 1100. Full-page capture expands the content scroll area equally before and after.

The baseline has no search, and inactive accounts expand beneath the active table. A failed refresh replaces the baseline table and preserves it in the updated view. The create and edit dialogs retain their existing layout and behavior. In the final comparison, all six roles appear inline before; after, the primary role and a +5 control keep the row compact and open the complete role list. The existing narrow-window desktop titlebar overlap remains visible in both versions and is outside this page change.

Validation: production build, 8 native helper tests and 33 browser checks pass. Browser checks cover search, role/access filters, pagination, snapshot replacement, loading/empty/error recovery, existing account actions with signed fixture requests, and light/dark layouts. Dedicated multi-role checks cover row height, all six labels, hidden-role filtering, keyboard activation, Escape/focus restoration, outside-click dismissal, inactive accounts and unclipped popovers. A read-only Electron refresh against the configured central backend also passed. The branch merges with the pending multi-key feature without conflicts, and that merged result builds successfully.

Result files and PNG SHA-256 hashes are included beside the images.

## User management — desktop

| Before | After |
| --- | --- |
| ![Before: User management — desktop](before/01-overview.png) | ![After: User management — desktop](after/01-overview.png) |

[Full-size comparison](comparisons/01-overview.png)

## User management — dark theme

| Before | After |
| --- | --- |
| ![Before: User management — dark theme](before/02-dark.png) | ![After: User management — dark theme](after/02-dark.png) |

[Full-size comparison](comparisons/02-dark.png)

## Inactive accounts — expanded section before, directory filter after

| Before | After |
| --- | --- |
| ![Before: Inactive accounts — expanded section before, directory filter after](before/03-inactive.png) | ![After: Inactive accounts — expanded section before, directory filter after](after/03-inactive.png) |

[Full-size comparison](comparisons/03-inactive.png)

## User management — narrow window

| Before | After |
| --- | --- |
| ![Before: User management — narrow window](before/04-mobile.png) | ![After: User management — narrow window](after/04-mobile.png) |

[Full-size comparison](comparisons/04-mobile.png)

## Search — unavailable before, clear no-match state after

| Before | After |
| --- | --- |
| ![Before: Search — unavailable before, clear no-match state after](before/05-no-matches.png) | ![After: Search — unavailable before, clear no-match state after](after/05-no-matches.png) |

[Full-size comparison](comparisons/05-no-matches.png)

## User management — empty directory

| Before | After |
| --- | --- |
| ![Before: User management — empty directory](before/06-empty.png) | ![After: User management — empty directory](after/06-empty.png) |

[Full-size comparison](comparisons/06-empty.png)

## User management — failed refresh

| Before | After |
| --- | --- |
| ![Before: User management — failed refresh](before/07-refresh-error.png) | ![After: User management — failed refresh](after/07-refresh-error.png) |

[Full-size comparison](comparisons/07-refresh-error.png)

## User management — create user dialog

| Before | After |
| --- | --- |
| ![Before: User management — create user dialog](before/08-create.png) | ![After: User management — create user dialog](after/08-create.png) |

[Full-size comparison](comparisons/08-create.png)

## User management — edit user dialog

| Before | After |
| --- | --- |
| ![Before: User management — edit user dialog](before/09-edit.png) | ![After: User management — edit user dialog](after/09-edit.png) |

[Full-size comparison](comparisons/09-edit.png)

## User management — loading state

| Before | After |
| --- | --- |
| ![Before: User management — loading state](before/10-loading.png) | ![After: User management — loading state](after/10-loading.png) |

[Full-size comparison](comparisons/10-loading.png)

## Six assigned roles — inline before, on demand after

| Before | After |
| --- | --- |
| ![Before: Six assigned roles — inline before, on demand after](before/11-roles.png) | ![After: Six assigned roles — inline before, on demand after](after/11-roles.png) |

[Full-size comparison](comparisons/11-roles.png)

