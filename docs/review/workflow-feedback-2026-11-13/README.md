# Contract workflow feedback — 13 November 2026

These assets are on a separate review branch and are not part of any functional PR diff. All people, account names and workload definitions shown are synthetic review data. Only this explicit screenshot/report allowlist was published; no test account credentials, private keys, plaintext contracts or application profiles are included.

## Exact sources

IBM contract-ui main: `fffc60e0f5690b968604bb02fafede8e90b81171`. IBM contract-manager main: `0ad049a052b37ae96d3f9106d5661236214e00eb`.

- imports: `886b34b7f7314b064cb132c24580f372ebf52ef0`
- attestation: `28d952b5940dc5cdd36edd73596ad18b2e19cbb4`
- receipts: `b5638d142f1711e1542490b61ba522cff0330c12`
- backend: `1de6b46419fc88b4990fbb6450c71cf88fcd35da`

Each after screenshot renders its single UI PR directly on IBM main. Before screenshots render unchanged IBM main. Both sides use the actual React/Carbon components with synthetic API/IPC fixtures. The importer fixture calls the actual Node main-process workload preparer from the importer PR. The images are direct browser captures, not design mockups.

The backend HPVS pair renders the same unchanged IBM main UI on both sides: the API capability response changes from CCRT-only to CCRT plus HPVS. The after certificate response comes from the updated backend catalog for HPVS 1.0.30. This pair illustrates the backend response, not a frontend redesign.

## Independent verification

All three UI branches passed npm test (23 tests), node --test tests (92 helper tests on the importer branch; 85 existing helper tests for each other branch) and npm run build separately. Browser interaction checks passed for upload addition/removal/replacement, invalid batches, preservation of environment settings, delayed certificate reads, invalid certificates, evidence removal, 16 px attestation spacing, receipt clipboard content and encrypted-payload preview. White and g100 themes were checked. Receipt cards and complete hashes fit 390 px and 720 px windows. The importer dialog fits 720 px.

All six orders of merging the three UI PRs are conflict-free and produce one identical tree. Their combined source exactly matches the previously verified integration at 0dbe32a; only documentation was reorganized between PRs. Each can merge on its own. The backend capability/prefix change also works with current main UI.

Backend checks passed: TEST_DATABASE_URL=... go test -race -count=1 ./... (real disposable PostgreSQL 16), go vet ./..., go build ./.... Tests cover shipped HPVS certificates, unchanged CCRT envelopes, all three encrypted payload types and independent legacy-envelope round trips with a disposable certificate.

## Full contract flows and limits

Three separate real Electron → HTTP → PostgreSQL flows used synthetic Admin, Auditor, Solution Provider, Data Owner and Environment Operator accounts. Each completed build creation/assignments, signing-key registration, workload and environment submission, attestation-key registration, finalization, export/download acknowledgment, integrity and audit checks. The Compose and Podman flows each have two persistent volumes. The Pod references its uploaded ConfigMap and both volume mounts. Independent OpenSSL/Node decryption recovers all three sections, exact seeds and original workload definitions; signatures verify and tampering is rejected. The HPVS flow fetched the real HPVS 1.0.30 certificate through all three forms, made 13 successful signed mutations, exported three hyper-protect-basic envelopes and passed independent signature/tamper checks. IBM runtime private keys are unavailable, so real HPVS runtime decryption was not tested; the disposable catalog round-trip test covers that wire format.

Local tools: Node 26.10.0/npm 11.19.1, below package engine declarations 26.13.1/12.2.2. Electron full flows used the locally available 44.7.2 binary, rather than declared 45.3.1. Isolated test profiles used an AES-GCM safeStorage adapter because unattended OS keychain access was unavailable; production safeStorage is unchanged. Crypto IPC, request signing, authorization, database operations, section encryption and final signatures are real. No Z16 workload was redeployed; OS keychain integration, distributable packaging and real IBM attestation evidence were not exercised.

A rapid earlier local HPVS run hit certificate-endpoint HTTP 429 and correctly displayed Retry. A paced rerun completed; no rate limit was changed. GitHub CI status is tracked in each PR, not asserted by these local reports.
