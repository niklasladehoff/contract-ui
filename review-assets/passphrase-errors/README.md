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

# Passphrase error comparison

Review images for contract-manager issue #16 and contract-ui issue #136.

Actual React/Carbon signing-key registration components captured in isolated Electron profiles, using deterministic service responses matching the old generic registration error and new specific uppercase-rule error. Cropped to the notification; no real credentials are shown.

Before: contract-ui public main 2dfae923b0d3bc46037f0b2f325e3834a5f0b518.
After: UI c3d98471d1689d409a1dbb18334ddb2eeb4c9c08 with the error from backend 788ef72b3587a227782015510c9791e99a36a5a2, based on validation PR #13.

This compares combined backend/UI behavior. The UI fix changes three payload expressions; it does not redesign the notification or change its copy. The more precise error comes from the backend.

Real HTTP/PostgreSQL integration is verified separately in the backend regression test, including key generation, finalization, independent contract signature verification and retry state. Attestation record decryption/signature operations are stubbed in that test; these images do not claim to verify IBM attestation evidence.
