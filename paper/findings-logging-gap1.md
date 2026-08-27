# Finding: Logging absence in Bašić v4 — Gap 1 worked example

**Status:** Evidenced (PDF-verified 2026-08-27).  
**Paper placement:** primary Gap 1 worked example (results / artifact section) — not only threats to validity.

## Evidenced claim

Bašić & Giaretta (arXiv:2412.15004**v4**) synthesise vulnerabilities in LLM-generated code **“as identified in 21 studies”** into ten categories (Section 4 / Table 3). Across that paper:

| Check | Result |
|---|---|
| CWE-778 Insufficient Logging | **Absent** |
| CWE-779 | **Absent** |
| CWE-223 Omission of Security-relevant Information | **Absent** (bare “223” hits are dataset sizes) |
| CWE-532 Sensitive Information in Log File | **Absent** (bare “532” hits are dataset sizes) |
| CWE-1295 | **Absent** |
| Word “logging” as topic | **Zero** topical uses (only sanitizer/crash-log contexts) |
| Log-adjacent CWE present | **CWE-117** only (Improper Output Neutralization for Logs), listed under Error Handling |

**Conclusion:** A taxonomy consolidating LLM-code vulnerabilities across 21 studies has **no category that assesses whether audit/access logging exists or is sufficient.**

## Set against Indian health-data obligations

| Obligation | Source | Dimension |
|---|---|---|
| Visibility of personal-data access via logs, monitoring, review | DPDP Rules **r.6(1)(c)** | `access_logging_demonstrability` |
| Strict audit trail of processing activities with access to personal data | ABDM HDMP **cl.27.5(a)** | `access_logging_demonstrability` |

A module can be fully remediated under every Bašić category (including CAT-10’s CWE-117) and still supply **no** evidence toward these criteria. Under the cell-coding rule, that is **`not_visible`** across the logging column — not a creative stretch to “partial.”

## Why CWE-117 is not a rescue

CWE-117 presupposes that logs exist and concerns neutralizing unsafe content written *to* them. An RCM under CAT-10 therefore does not guarantee access-logging existence or sufficiency. Pilot cell **CAT-10 × OB-DPDP-R-006-02** is the instructive discrimination.

## Implication for Gap 1

This is the cleanest instance of Gap 1: CWE/OWASP-shaped LLM-code security assessment does not express a demonstrability duty that Indian health-data regulation makes mandatory. The extended taxonomy therefore adds `access_logging_demonstrability` as an obligation-level dimension with no Bašić home.
