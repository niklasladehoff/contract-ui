<!--
Copyright (c) 2026 IBM Corp.
All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Runtime certificate selector review

Public review images for ibm-hyper-protect/contract-ui#134 and
ibm-hyper-protect/contract-manager#14. This branch holds image assets only;
it is not intended to merge into either feature branch.

- Before: public UI main `2dfae923b0d3bc46037f0b2f325e3834a5f0b518`.
- After: UI `582f4e9929c88b4564e92977a56b60e706dd89a8`, on validation PR #133.
- Backend: `f4e74f3f0d4a7f23b3836fca3870f64a6e1d36cd`, on validation PR #13.
- Captured in isolated Electron profiles at a 1600 × 1000 viewport.
- Images crop the actual certificate panels in Add workload, Add environment
  and Add attestation. Build display data uses deterministic fixtures.
- After images fetch the catalog and genuine CCRT 26.7.2 PEM through the real,
  authenticated local Go API. Signed schema preflight was also exercised.
- Before images show the old region/Production Certificate options; that UI
  does not fetch the new certificate API.
- No account credentials, access tokens or private keys are present.

Verified: stale-response protection; platform/source/server reset; expired,
empty, mismatched and failed responses; retry; supported/unsupported targets;
1024-pixel layout; isolated Carbon g100 picker. No renderer exceptions.

The four certificate catalogs in the pinned contract-go v2.37.0 library are
CCCO, CCRT, CCRV and HPVS. Only CCRT is supported by the current contract
workflow; the other catalog entries cannot enable submission in this UI.

A separate real HTTP workflow used CCRT 26.7.2 for workload, environment and
attestation, finalized the contract, and verified its signed encrypted export.
This is not a guest boot test. IBM runtime private keys are not available to
this review, so those production certificate ciphertexts were not decrypted.
