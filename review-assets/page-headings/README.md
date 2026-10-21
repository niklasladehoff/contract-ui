# Page headings — before and after

Review images for consistent page typography in Contract UI.

Before: public main `acc57cce69862ad9e67a6535927074ad488335ac`.
After: `1d93e9081f32185855e4bb4ed16cd5b70d741e2c` on `fix/consistent-page-headings`.

All images show actual React/Carbon components and the application shell with identical example accounts and mocked read-only API responses. No central account data, credentials or private keys are included. Viewport: 1600 × 1100, white theme. Account Settings is included as the reference.

Download and extract `page-headings-before-after.zip`, then open `index.html` for the interactive gallery. The `before/` and `after/` folders contain full-size originals. The `comparisons/` folder contains side-by-side PNGs with before on the left and after on the right.

## Views

| Page or tab | Before | After | Comparison |
| --- | --- | --- | --- |
| Home | [Before](before/01-home.png) | [After](after/01-home.png) | [Side by side](comparisons/01-home.png) |
| Build management — active builds | [Before](before/02-build-management.png) | [After](after/02-build-management.png) | [Side by side](comparisons/02-build-management.png) |
| Build details — assignments | [Before](before/04-build-assignments.png) | [After](after/04-build-assignments.png) | [Side by side](comparisons/04-build-assignments.png) |
| Build details — audit trail | [Before](before/05-audit-trail.png) | [After](after/05-audit-trail.png) | [Side by side](comparisons/05-audit-trail.png) |
| Diagnostics & analytics — overview | [Before](before/06-analytics.png) | [After](after/06-analytics.png) | [Side by side](comparisons/06-analytics.png) |
| Diagnostics & analytics — credential rotation | [Before](before/07-credential-rotation.png) | [After](after/07-credential-rotation.png) | [Side by side](comparisons/07-credential-rotation.png) |
| User management | [Before](before/08-user-management.png) | [After](after/08-user-management.png) | [Side by side](comparisons/08-user-management.png) |
| System logs | [Before](before/09-system-logs.png) | [After](after/09-system-logs.png) | [Side by side](comparisons/09-system-logs.png) |
| Account settings — reference | [Before](before/10-account-settings.png) | [After](after/10-account-settings.png) | [Side by side](comparisons/10-account-settings.png) |
| Log in | [Before](before/11-login.png) | [After](after/11-login.png) | [Side by side](comparisons/11-login.png) |
| Server configuration | [Before](before/12-server-configuration.png) | [After](after/12-server-configuration.png) | [Side by side](comparisons/12-server-configuration.png) |
| Page not found | [Before](before/13-not-found.png) | [After](after/13-not-found.png) | [Side by side](comparisons/13-not-found.png) |
| Build details — signing key | [Before](before/14-signing-key.png) | [After](after/14-signing-key.png) | [Side by side](comparisons/14-signing-key.png) |
| Build details — workload | [Before](before/15-workload.png) | [After](after/15-workload.png) | [Side by side](comparisons/15-workload.png) |
| Build details — environment | [Before](before/16-environment.png) | [After](after/16-environment.png) | [Side by side](comparisons/16-environment.png) |
| Build details — attestation key | [Before](before/17-attestation-key.png) | [After](after/17-attestation-key.png) | [Side by side](comparisons/17-attestation-key.png) |
| Build details — finalise contract | [Before](before/18-finalise.png) | [After](after/18-finalise.png) | [Side by side](comparisons/18-finalise.png) |
| Build details — export contract | [Before](before/19-export.png) | [After](after/19-export.png) | [Side by side](comparisons/19-export.png) |
| Build details — attestation records | [Before](before/20-attestation-records.png) | [After](after/20-attestation-records.png) | [Side by side](comparisons/20-attestation-records.png) |
| Build details — verify attestation | [Before](before/21-verify-attestation.png) | [After](after/21-verify-attestation.png) | [Side by side](comparisons/21-verify-attestation.png) |

## Validation

The local production build passes. Browser checks cover all 20 desktop views, 80 responsive/theme cases and 13 interactions/loading/error states. The existing Electron preview also renders the shared header while using the central backend. These are local checks; GitHub CI is pending publication.

Only presentation components and SCSS change in the code branch. API services, auth stores, IPC, main-process code and dependencies are unchanged. This change has no dependency on the separate multi-key work.
