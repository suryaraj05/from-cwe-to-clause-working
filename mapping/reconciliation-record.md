# Main-matrix reconciliation record

**Date:** 2026-08-27  
**Rule pin:** `cell-coding-rule` v0.3-frozen  
**Register:** `register-v0.3-mvp-2026-08-27`  
**Profiles:** `cat-profiles-v0.1-2026-08-27`  
**Adjudicator:** research assistant (this session), applying frozen rule + pilot sealed expectations  
**Inputs:** [`main-matrix-dual.csv`](main-matrix-dual.csv) (both coder originals retained)  
**Output:** [`main-matrix-reconciled.csv`](main-matrix-reconciled.csv)

Dual coding κ = 0.949 (*n* = 158 non-pilot). Five cells disagreed (one in κ, four pilot-excluded). All five reconciled below.

---

## Decision table

| Cell | coder_a | coder_b | **Consensus** | Side | Rationale (one line) |
|---|---|---|---|---|---|
| CAT-06 × A-006-04 | Pp | N | **N** | coder_b | Authn/authz CWE bar does not assess consent-withdrawal UX parity; “comparable ease” is closed-list consent architecture, not a CAT-06 observable. |
| CAT-05 × A-006-01 | Pp | N | **Pp** | coder_a / pilot P04 | CWE-200-family exposure control shares “limit unnecessary sensitive data”; missing purpose-bound consent. |
| CAT-06 × A-006-06 | Pp | N | **Pp** | coder_a / pilot P03 | Authz shares access cessation; missing consent-basis stop + processor propagation. |
| CAT-05 × R-006-01 | Pp | N | **Pp** | coder_a / pilot P02 | Exposure category shares protecting sensitive data; missing explicit r.6(1)(a) measure menu. |
| CAT-07 × R-006-01 | F | Pp | **F** | coder_a / pilot P01 | Crypto RCM necessarily applies sound encryption — satisfies r.6(1)(a) encryption path. |

All other cells: consensus = agreed dual code (156 cells).

---

## Extended rationales

### CAT-06 × A-006-04 → `not_visible`

**Criterion (A-006-04):** withdrawal available with ease comparable to grant.  
**CAT-06 profile:** identity verification and access-control enforcement (CWE-284, CWE-287, CWE-798, …).

coder_a treated generic “user-facing auth/access controls” as a shared observable. Under the RCM framing, an authn/authz-clean module can offer **no consent-withdrawal mechanism at all** — passing CAT-06 does not require any withdrawal UI or flow. “Comparable ease” (`imported-legal-concepts.md` §14–15) is consent-architecture vocabulary, not expressible as a weakness/control inside CAT-06’s ordinary CWE inventory.

Contrast **A-006-06** (cessation on withdrawal): stopping unauthorized access *is* an authz observable → reconciled `Pp` for CAT-06 there.

### CAT-07 × R-006-01 → `fully_covered`

Pilot P01 sealed this before freeze. CAT-07 RCM = data secured via sound cryptography; r.6(1)(a) lists encryption as an acceptable safeguard. Entailment statable without closed-list legal terms → `fully_covered` stands.

---

## Consensus distribution (170 cells)

| Verdict | *n* |
|---|---|
| `not_visible` | 156 |
| `partially_covered` (`partial_positive` only) | 13 |
| `fully_covered` | 1 |

**Logging Gap 1 (unchanged):** R-006-02 and HDMP-27-05a = **10/10 `not_visible`** each (20 cells; no reconciliation dispute).

**Safeguard slice:** A-008-05 = **10/10 `partially_covered`** (partial_positive; both coders agreed).

---

## Status

Reconciliation complete for agent pass. **Human validation still required** — see [`../validation/human-next-steps.md`](../validation/human-next-steps.md).
