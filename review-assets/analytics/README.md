# Analytics rework — before and after

The overview prioritizes credential issues, groups build/user metrics, and uses readable horizontal role charts. Credential health replaces four nested tabs with credential/status filters, searchable accounts and confirmed bulk actions.

Before: the [heading PR #101](https://github.com/ibm-hyper-protect/contract-ui/pull/101) plus public main `4800b92` (baseline `fdb5cd1`). After: analytics commit `6a35dcb` on `fix/analytics-dashboard-carbon`. This follow-up depends on the shared header from #101 and has no multi-key backend dependency.

Actual React/Carbon views with identical example accounts and mocked API responses, captured at a 1600 × 1100 viewport. The scrollable content area is expanded equally in both versions so full charts and legends are visible. No real central account data is shown, and credential operations were tested only against mocks.

Local validation passes: production build, nine credential expiry tests, 13 browser behavior/state checks, and 16 responsive/theme combinations. The API services, auth stores, IPC and main-process code are unchanged.

## Analytics overview

<table>
<tr><th>Before — Analytics overview</th><th>After — Analytics overview</th></tr>
<tr><td><img width="640" alt="Before: Analytics overview" src="before/01-overview.png" /></td><td><img width="640" alt="After: Analytics overview" src="after/01-overview.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/01-overview.png)

## Credential health — passwords

<table>
<tr><th>Before — Credential health — passwords</th><th>After — Credential health — passwords</th></tr>
<tr><td><img width="640" alt="Before: Credential health — passwords" src="before/02-password-review.png" /></td><td><img width="640" alt="After: Credential health — passwords" src="after/02-password-review.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/02-password-review.png)

<details>
<summary>Credential health — public keys</summary>

<table>
<tr><th>Before — Credential health — public keys</th><th>After — Credential health — public keys</th></tr>
<tr><td><img width="640" alt="Before: Credential health — public keys" src="before/03-public-key-review.png" /></td><td><img width="640" alt="After: Credential health — public keys" src="after/03-public-key-review.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/03-public-key-review.png)

</details>

<details>
<summary>Credential health — upcoming key expiries</summary>

<table>
<tr><th>Before — Credential health — upcoming key expiries</th><th>After — Credential health — upcoming key expiries</th></tr>
<tr><td><img width="640" alt="Before: Credential health — upcoming key expiries" src="before/04-upcoming-expiries.png" /></td><td><img width="640" alt="After: Credential health — upcoming key expiries" src="after/04-upcoming-expiries.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/04-upcoming-expiries.png)

</details>

<details>
<summary>Analytics overview — dark theme</summary>

<table>
<tr><th>Before — Analytics overview — dark theme</th><th>After — Analytics overview — dark theme</th></tr>
<tr><td><img width="640" alt="Before: Analytics overview — dark theme" src="before/05-dark-overview.png" /></td><td><img width="640" alt="After: Analytics overview — dark theme" src="after/05-dark-overview.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/05-dark-overview.png)

</details>

<details>
<summary>Analytics overview — no data</summary>

<table>
<tr><th>Before — Analytics overview — no data</th><th>After — Analytics overview — no data</th></tr>
<tr><td><img width="640" alt="Before: Analytics overview — no data" src="before/06-no-data.png" /></td><td><img width="640" alt="After: Analytics overview — no data" src="after/06-no-data.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/06-no-data.png)

</details>

<details>
<summary>Credential health — no issues</summary>

<table>
<tr><th>Before — Credential health — no issues</th><th>After — Credential health — no issues</th></tr>
<tr><td><img width="640" alt="Before: Credential health — no issues" src="before/07-healthy-credentials.png" /></td><td><img width="640" alt="After: Credential health — no issues" src="after/07-healthy-credentials.png" /></td></tr>
</table>

[Open full-size comparison](comparisons/07-healthy-credentials.png)

</details>
