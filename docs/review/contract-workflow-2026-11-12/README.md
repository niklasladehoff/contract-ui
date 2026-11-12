# Multi-volume import and build passphrase review

Source: IBM contract-ui main `51821d0`, Compose feature `efd6b36`, passphrase feature `2072923`; backend main `fe462ef` plus normalization follow-up `e362e13`.

The before/after passphrase captures render the actual React/Carbon components against deterministic synthetic service responses. The before capture uses IBM main; the after capture uses the passphrase PR alone. Compose captures show the actual multi-volume component and generated YAML, using its real Node preparation module through a review bridge. Screenshots and evidence are outside the functional PR diffs.

`compose-browser-result.json` records add/remove, duplicate rejection, exact seed preservation, and no automatic submission. `full-flow-result.json` records a separate complete Electron run against a real local Go backend/PostgreSQL: five persona accounts and device keys, build/assignments, signing registration with surrounding spaces, Compose with two volumes, environment validation/submission, attestation registration, finalization, export acknowledgment, contract integrity and audit verification. All 13 authenticated mutations succeeded and carried request signatures; no renderer exceptions.

`export-verification.json` records independent OpenSSL/Node decryption of the exported sections, exact volume seed and Compose archive checks, RSA signature verification and tamper rejection. The synthetic runtime certificate/private key are disposable and are not published here. No production credentials, contracts or registry API keys are included.

The full-flow launcher substitutes an isolated AES-GCM adapter for macOS safeStorage because the test Electron profile cannot access the OS keychain unattended. Production storage code is unchanged. RSA key generation, IPC, request signing, backend authorization, database operations, contract encryption and signing are real. This does not test OS keychain integration, guest deployment or real IBM attestation evidence. The backend HTTP integration suite tests evidence unlock/retry behavior with a stubbed attestation-record engine.

Checks: Compose PR `node --test tests` (85), `npm test` (22), production build; passphrase PR helper suite (65), `npm test` (23), production build. Backend `TEST_DATABASE_URL=... go test -race -count=1 -v ./...`, `go vet ./...`, `go build ./...` passed with all PostgreSQL integration tests enabled. Both UI merge orders produce the same tree `41ffca9b78302285c141f248c47671e5abece6dc`.
