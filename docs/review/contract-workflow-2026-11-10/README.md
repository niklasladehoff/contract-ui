# Contract workflow review images

Before screenshots use IBM `main` at `b34cabe785a230b3a2df4efb4e7dd90138d0cd38`. After screenshots render each feature independently on the same base. Application code is unchanged by this assets branch.

All screenshots use synthetic accounts/builds and a disposable public test certificate. No deployment credentials, private keys or live-backend data are included. Reduced motion is enforced for stable captures. Certificate and form screenshots are focused component captures.

| Improvement | Feature commit | Tests |
| --- | --- | --- |
| feat/compose-workload-import | `a40da665a2b2dcdf4d251245a42638291c0801ad` | 72 passing |
| feat/build-certificate-reuse | `bfe5cf57a25fafedb944f2b2054f25c9981c2e03` | 58 passing |
| feat/build-role-handoff | `426a09cd11cba644fd3f4bbcd26d22badd5fa32f` | 57 passing |
| feat/contract-input-guidance | `ececd94ed5c1670756da9ba20869f576f2ee4417` | 54 passing |

Each feature builds independently. All 24 merge permutations succeed against this IBM main snapshot. The combined tree builds and passes 79 tests. Browser review covers import/YAML review, explicit certificate reuse and session boundaries, role handoff with stage/assignment rechecks, dark theme, narrow layouts and keyboard use. The two new main-process capabilities were also exercised through the real Electron preload and IPC handlers.

Screenshot fixtures do not demonstrate a live IBM Z deployment. Review this change with the related issue and PR in the IBM repository.
