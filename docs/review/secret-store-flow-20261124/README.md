# Personal Secret Store and approved build flow — review evidence

Captured 24 November 2026. Images are kept on a separate review-assets branch,
not in the application PR's diff.

## Sources

- Before: IBM `contract-ui` main `6f4dc27a6ccc04b9018fb0866f078f738f47718b`.
- After UI: `78b1aca6c9e7ff6a632c36f394d27c9c6d6178a2`.
- Manager: `f2c63035b502235f5507e2248574c6b9ffbde105`.
- UI includes Samuel's PR 180 at `207abae056e666eabd19a289a499eb802d1d496d`.
- Manager includes PR 40 at `f675f1148f5ae1d386a06e5a900fe36d0d544358`
  and runtime/configuration PR 37 at `3f68ad97ef62554cd096e92c9aed7bd35f120981`.
- Prepared-contract dependency: pinned contract-go PR 344 revision
  `2df57ea38fa4c4d5c965ed1db8e4c4d1cb2684da`, including its validation fixes.

## Capture provenance

The images render the actual React/Carbon components in headless Chromium.
Before uses an isolated worktree at IBM main. After uses the committed feature
source. Both read the existing disposable demo Manager's real data. A Node-side,
read-only HTTP relay permits the isolated screenshot origin; it removes the
screenshot origin before forwarding and does not change production CORS settings
or fabricate API results. Electron functionality is bridged to the running real
Electron main process over CDP; no renderer-side cryptography is substituted.

The desktop-sized images use 1440 × 1000 CSS pixels. The Runtime secrets image is
a component crop rendered in a taller 1440 × 1800 viewport so all three steps fit.
The before assignments page and after flow use the same completed synthetic build.
The target-help images use a separate disposable, editable build. Font assets are
served read-only from the installed project dependencies for the isolated main
worktree. There is no image compositing or replacement of form text.

All names, accounts and catalog aliases belong to synthetic demo fixtures.
Public UV IDs identify requests; they do not grant access. No stored secret values,
private keys, credentials or authentication tokens are shown or included here.

## Images

- `before-main-assignments.png`: IBM main has assignments but no private store
  navigation or Runtime secrets workflow.
- `after-personal-secret-store.png`: personal encrypted catalog.
- `after-personal-groups.png`: personal groups with stable table dimensions.
- `after-runtime-secrets.png`: approved target, approving account/time and prepared
  public IDs; explicit development-simulation warning.
- `after-target-field-help.png`: SE-header input and trusted-source guidance.
- `after-hkd-field-help.png`: destination HKD guidance, independent of Manager host.

## Validation and limits

- Manager full suite with race detector, real disposable PostgreSQL and genuine
  pvsecret: 335 passing test cases, zero failures and zero skips.
- UI suite: 33 passing tests; production build passed.
- `go vet ./...`, changed-code gofmt and `git diff --check` passed. SQLC outputs
  were regenerated through the repository's generation script.
- Manager, worker and consumer compile for macOS/arm64 and Linux/s390x.
- Eleven target help controls were checked in real Electron: hover, keyboard focus,
  Escape, unchanged field values, unchanged profile selection and no file picker
  or mutating HTTP request. Escape on a hovered hint also preserves the dialog
  when focus remains inside an input.
- Earlier complete signed Electron flows exercised owner consent, groups,
  preparation, workload/environment submission, attestation registration,
  finalization, native Save and signed download acknowledgement. Downloaded
  sections were independently checked. See the Manager's validation record.
- Local versions: Go 1.27.1; Node 26.10.0; npm 11.19.1. Node/npm are below the
  upstream package's declared engines; no desktop packaging is claimed here.
- Compatible transitive npm security updates are included. Existing moderate
  electron-builder packaging advisories require separate breaking upgrades.

The displayed requests are genuine offline pvsecret requests in explicit
SIMULATION. This is not native UV Add/Retrieve acceptance or deployment of this
secret flow. The tested Z16 lacks retrievable Add/Retrieve; a compatible target
kernel, Ultravisor and runtime, current verified HKDs/CRLs and runtime provisioning
are required for native use. There is no automatic software fallback.

Optional worker-container recipes were inspected but not run with a production
pvsecret tools image. The workload consumer is an opt-in helper with a restricted
private Unix socket; container/device isolation must be provisioned by the operator.
