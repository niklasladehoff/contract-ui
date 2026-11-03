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

# Contract input validation — UI comparisons

Representative states captured from the actual React/Carbon app in isolated Electron profiles using deterministic local API fixtures, not a live production backend. All images use a 1600 × 1000 viewport, white theme, the same example identity and workload. Public disposable certificate data is used; no private keys or real credentials are included.

Before: public UI main `2dfae92`. After: the contract-input feature; the original matched images use `fc952af`, and the additional legacy image includes the compatibility follow-up in this feature branch. Capture metadata records the fixtures, request paths and checks. Cryptographic correctness is verified separately by the real backend/API integration tests.

| State | Before | After |
|---|---|---|
| Workload input | [Before](workload-input-before.png) | [After](workload-input-after.png) |
| Workload review | [Before](workload-review-before.png) | [After](workload-review-after.png) |
| Attestation certificate | [Before](attestation-certificate-before.png) | [After](attestation-certificate-after.png) |

[Legacy-server review](legacy-review-after.png) shows explicit syntax-only validation and unavailable-history notices. The fixture checks also cover 500 errors, normalized selected-section submission, retry and duplicate-submission stage gating.
