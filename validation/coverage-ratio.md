# Coverage ratio (documentary — MVP scope)

**Purpose:** Hevner evaluation metric — how much of the targeted regulatory surface the obligation register currently captures.  
**Status:** MVP counts; **unchanged register** (`register-v0.3-mvp-2026-08-27`); matrix counts refreshed after human sample (2026-11-14).  
**Register pin:** `register-v0.3-mvp-2026-08-27`

---

## Counts

| Metric | Value | Notes |
|---|---|---|
| Register rows (MVP) | **18** | Includes HDMP-16-04 (org-policy / underspecified for code) |
| Rows in Gap-1 matrix | **17** | HDMP-16-04 excluded from 10×17 matrix |
| Matrix cells coded (consensus) | **170** | 10 Bašić categories × 17 obligations |
| Primary instruments represented | **4** | DPDP Act, DPDP Rules, ABDM HDMP, NRCeS FHIR IG v6.5.0 |
| Obligation families in MVP | **7** | consent/notice, security, logging, breach, retention, localization, ABDM technical |

---

## Family coverage (MVP register vs stated project scope)

| Family | MVP rows | In matrix | Consensus non-`not_visible` cells |
|---|---|---|---|
| Consent / notice (Act s.6, Rules r.3) | 6 | 6 | 2 partial (CAT-05×A-006-01; CAT-06×A-006-06) |
| Security safeguards (Act s.8(5), Rules r.6(1)(a)) | 2 | 2 | 10 partial (A-008-05: 8 Pp/Pd; R-006-01: CAT-05 + CAT-07) — **no** full |
| Access logging (Rules r.6(1)(c), HDMP 27.5(a)) | 2 | 2 | **0** — Gap 1 (20/20 `not_visible`) |
| Breach (Act s.8(6), Rules r.7) | 3 | 3 | 0 |
| Retention / erasure (Act s.8(7)) | 1 | 1 | 0 |
| Localization (Act s.16) | 1 | 1 | 0 |
| ABDM identity / FHIR | 3 | 2 in matrix | 0 in matrix (16-04 excluded) |

---

## Instrument-level coverage (honest bounds)

### DPDP Act 2023 (selected sections only)

MVP rows touch: **s.6(1), (4), (6); s.8(5)–(7); s.16(1)** — commencement +18m → **2027-05-13** per G.S.R. 843(E).

**Not in MVP register (examples of gaps):** s.7 legitimate uses, s.9–10 data-principal rights in full, s.11–14 grievance/DPO/SDF machinery, s.12 nomination, full s.8 family beyond cited subsections.  
**Ratio (illustrative):** 8 atomic criteria derived from ~6 Act sections / **partial Act coverage** — do not report as “X% of DPDP Act.”

### DPDP Rules 2025 (selected rules only)

MVP rows touch: **r.3(b)–(c), r.6(1)(a)(c), r.7(1)–(2)**.

**Not in MVP:** consent-manager mechanics (r.4+), full notice schedule, many operational rules.  
**Ratio:** partial Rules coverage by design (pilot corpus).

### ABDM HDMP

MVP rows: **cl.15.4, 16.4, 27.5(a)**. HDMP has additional clauses (consent artefacts, retention, security-by-design elsewhere) not yet rowed.

### NRCeS FHIR IG v6.5.0

MVP: **one conformance row** (profile/`StructureDefinition` expectation). Full IG has many profiles — **one row ≠ IG exhaustiveness**.

---

## Matrix visibility ratio (post human sample, 2026-11-14)

Among **170** reconciled cells:

| Consensus | *n* | % |
|---|---|---|
| `not_visible` | **158** | 92.9% |
| `partially_covered` | **12** | 7.1% |
| `fully_covered` | **0** | 0% |

Earlier agent consensus was 156 N / 13 P / 1 F. Human sample adjudication removed the sole `fully_covered` cell (CAT-07 × R-006-01 → Pp) and two A-008-05 partials (CAT-08/09 → N).

**Interpretation:** For the MVP obligation set, Bašić’s ten CWE-shaped categories **do not** collectively surface most Indian regulatory observables. Logging columns are uniformly `not_visible` — the strongest structural gap.

---

## Reporting guidance (paper)

- Report **MVP register size** and **matrix counts** as measured (158/12/0).  
- Do **not** claim “X% of DPDP compliance” without a defined denominator agreed with mentor.  
- Treat this file as **instrument scope transparency**, not a compliance score.

**Human follow-up:** expand register deliberately by family; recompute coverage when register version bumps.
