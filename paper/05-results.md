# 05 Results

**Status:** updated 2026-11-14 — includes human sample coding + Bahmni HIP case study.  
**Pins:** rule `v0.3-frozen` · register `register-v0.3-mvp-2026-08-27` · profiles `cat-profiles-v0.1-2026-08-27`  
**Artifacts:** [`mapping/main-matrix-reconciled.csv`](../mapping/main-matrix-reconciled.csv) · [`mapping/human-sample-results.md`](../mapping/human-sample-results.md) · [`../validation/case-study-report.md`](../validation/case-study-report.md)

---

## 5.1 Cross-mapping coverage (10 × 17 = 170 cells)

| Consensus verdict | *n* | % of 170 |
|---|---|---|
| `not_visible` | **158** | 92.9% |
| `partially_covered` | **12** | 7.1% |
| `fully_covered` | **0** | 0% |

Counts reflect the **human sample patch (2026-11-14)**. An earlier agent dual-coding pass reported 156 N / 13 P / 1 F; human adjudication moved CAT-07 × R-006-01 from `fully_covered` to `partially_covered` and CAT-08/09 × A-008-05 from partial to `not_visible`.

### Interpretation

Most MVP Indian regulatory observables are **not guaranteed** by remediating any single Bašić CWE-shaped category. Emptiness is an outcome supporting Gap 1, not a failure of the instrument.

Closest technical overlap: **CAT-07 × R-006-01** remains only **partial** — sound cryptography when used does not entail encryption/masking/tokenization of all personal data.

**A-008-05** (reasonable safeguards) is **not** uniform: several categories contribute a safeguard *slice* (`Pp`/`Pd`); Resource Management and Coding Standards do not (`N`).

### Columns with any non-`not_visible` cell (current)

| Obligation | Non-N pattern |
|---|---|
| A-006-01 | CAT-05 → P |
| A-006-06 | CAT-06 → P |
| A-008-05 | Mixed Pp/Pd; CAT-08/09 → N |
| R-006-01 | CAT-05 → P; CAT-07 → P (not F) |

All other MVP columns: uniformly `not_visible` across ten categories.

---

## 5.2 Human sample reliability (Phase 1)

Two human coders (Surya, Rahul) independently scored a **50-cell sample** (all 10 categories × five obligations: R-006-02, HDMP-27-05a, A-008-05, R-006-01, A-006-04) under the frozen rule, without consulting the reconciled CSV.

| Metric | Result |
|---|---|
| Raw agreement | **46/50 (92%)** |
| Disagreements adjudicated | 4 |
| Gap 1 (logging columns) | **20/20 `not_visible`** (unanimous; CAT-10 trap avoided) |

This human–human sample is the primary trust signal for matrix judgements. The earlier agent κ (0.949 on 158 non-pilot cells) is retained only as **exploratory** context: agreement ≠ correctness, and mass `not_visible` inflates κ ([`06-threats-to-validity.md`](06-threats-to-validity.md)).

Detail: [`../mapping/human-sample-results.md`](../mapping/human-sample-results.md).

---

## 5.3 Gap 1 — access logging

**Bašić v4 (PDF-verified):** no CWE-778/779/223/532/1295 as logging-existence weaknesses; topical “logging” absent; only CWE-117 (log *output* neutralization) under Error Handling.

| Obligation | Matrix (all 10 CATs) |
|---|---|
| R-006-02 (DPDP Rules r.6(1)(c)) | 10/10 `not_visible` |
| HDMP-27-05a (ABDM HDMP cl.27.5(a)) | 10/10 `not_visible` |

A module can be fully remediated under every Bašić category—including CAT-10—and still supply **no** evidence that access/audit logging exists. Full evidence note: [`findings-logging-gap1.md`](findings-logging-gap1.md).

---

## 5.4 Case study — Bahmni India Distro HIP (Phase 2)

**System:** public MIT repositories `BahmniIndiaDistro/openmrs-module-hip` and `hip-service` (ABDM Health Information Provider integration).  
**Method:** dual rubric scoring (Pass / Partial / Fail / NA) on 10 indexed source files; matrix used as hints only.  
**Scorers:** Surya, Rahul · pre-adjudication agreement **16/18 (88.9%)**.

| Consensus highlights | Score |
|---|---|
| R-006-02 access logs | **Fail** |
| HDMP-27-05a audit trail | **Partial** |
| R-006-01 encryption/masking/tokens | **Partial** (in-transit ECDH/AES-GCM; not full at-rest coverage) |
| A-006-01 purpose-scoped consent | **Pass** |
| A-006-06 cease-on-revoke | **Pass** |
| HDMP-15-04 Health ID linkage | **Pass** |
| Breach intimation / erasure | **Fail** |
| Notice UI / withdrawal UX | **NA** (outside HIP backend) |

**Overall mix:** 3 Pass · 4 Partial · 5 Fail · 6 NA.

### Evaluation claim

On real ABDM-adjacent healthcare code, CWE-oriented reading of exception handlers and controllers can focus on log injection or error leakage while **missing** statutory access-monitoring log existence—matching the matrix Gap 1 prediction. Duties that are matrix-`not_visible` (consent scoping, revoke-stop, Health ID) still appear when the **register + rubric** path is applied.

Full report: [`../validation/case-study-report.md`](../validation/case-study-report.md).

---

## 5.5 Other findings

- **WASA transparency:** no public official WASA specification located ([`findings-wasa-transparency.md`](findings-wasa-transparency.md)).  
- **HDMP cl.16.4:** retained as org-policy / `criterion_underspecified` for code-pattern mapping; excluded from Gap-1 matrix.  
- **Coverage:** MVP register = 18 rows / 17 in matrix; partial instrument coverage by design ([`../validation/coverage-ratio.md`](../validation/coverage-ratio.md)).

---

## 5.6 Inter-rater summary

| Layer | Result |
|---|---|
| Agent matrix κ (exploratory) | 0.949 (*n* = 158) |
| Human matrix sample | 92% raw agree (50 cells) |
| Human case-study rubric | 88.9% raw agree (18 obligations) |
