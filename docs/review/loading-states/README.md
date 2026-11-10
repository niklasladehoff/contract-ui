# Contextual loading states — visual review

Baseline: IBM `main` at `b34cabe785a230b3a2df4efb4e7dd90138d0cd38`.
Implementation: `5645a8378220982f5825a6a90cc9e2a96ab78ab8`.

These captures use the real React/Carbon components with synthetic backend and
Electron IPC fixtures. Requests are deliberately delayed to show pending states.
They contain no production accounts, credentials or contracts. Build Management,
User Management and System Logs retain Carbon table skeletons. PNGs use reduced
motion; the GIF records the animated Analytics state in the app.

| Area | Before | After |
| --- | --- | --- |
| Sign-in | ![Before](login-before.png) | ![After](login-after.png) |
| Home overview | ![Before](home-before.png) | ![After](home-after.png) |
| Analytics | ![Before](analytics-before.png) | ![After](analytics-after.png) |
| Initial build list | ![Before](builds-before.png) | ![After](builds-after.png) |
| User directory | ![Before](users-before.png) | ![After](users-after.png) |
| System logs | ![Before](logs-before.png) | ![After](logs-after.png) |
| Audit trail | ![Before](audit-before.png) | ![After](audit-after.png) |
| Workload context | ![Before](workload-before.png) | ![After](workload-after.png) |
| YAML template | ![Before](template-before.png) | ![After](template-after.png) |
| Signing key registration | ![Before](signing-before.png) | ![After](signing-after.png) |
| Password update | ![Before](password-before.png) | ![After](password-after.png) |
| Finalisation prerequisites | ![Before](finalise-before.png) | ![After](finalise-after.png) |
| Contract finalisation | ![Before](assembly-before.png) | ![After](assembly-after.png) |
| Contract export | ![Before](export-before.png) | ![After](export-after.png) |
| Attestation context | ![Before](attestation-before.png) | ![After](attestation-after.png) |

## Animation and accessibility

![Analytics loading in the app](loading-in-app.gif)

![Carbon dark theme](analytics-g100.png)

![All ten static illustrations under reduced motion](all-graphics-reduced-motion.png)

## Validation

- `npm run build` and `git diff --check` pass. No test runner exists in this repository.
- Delayed requests show activity and completed requests remove it.
- Build Management, User Management and System Logs show native Carbon table
  skeletons while pending; no SVG replaces those table layouts.
- Failed login, password, template and signing-key operations clear activity and allow retry.
- Finalisation and export complete successfully; pending transaction actions stay disabled.
- Configuration hydration completes on success and read failure; startup has no fake percentage.
- Carbon light/dark colors remain correct with the opposite OS color scheme.
- All ten illustrations remain static after a live reduced-motion change; normal motion animates.
- 390px layout fits its loading state; image is decorative and operation text uses a polite status region.
- All 120 merge orders with PRs #154–#157 merge without manual conflict resolution at the recorded heads.
- New SVG/component/style files carry the IBM Apache-2.0 header. Dependencies and Electron crypto are unchanged.
