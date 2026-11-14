# Conclusion

**Status:** updated 2026-11-14.

We presented a documentary framework for assessing whether patient-data modules exhibit patterns consistent with selected DPDP and ABDM obligations when reviewers use Bašić and Giaretta’s ten CWE-shaped vulnerability categories. The cross-mapping matrix, coded under a frozen counterfactual rule and patched after a human sample, shows that most regulatory observables in our MVP register are **not visible** through category remediation alone (**158/170** cells `not_visible`; **0** fully covered). The strongest structural instance is **access-logging demonstrability**: Indian rules require visibility of personal-data access, yet Bašić v4’s 21-study taxonomy includes no category that assesses log existence—confirmed across twenty matrix cells, PDF-verified absence of logging CWEs, and a Bahmni HIP case study where access logs scored **Fail**.

Human dual coding on a 50-cell sample reached **92%** raw agreement; dual rubric scoring on the case study reached **88.9%**. Agent κ remains exploratory. We extended the taxonomy with obligation-level dimensions, supplied an assessment rubric and short developer guide, and documented the lack of a public WASA specification rather than inventing register rows.

**Limitations:** MVP register scope; pattern assessment only; commencement dates largely 2027-05-13 for substantive duties; Delphi not executed (optional unless the guide requires it); mentor sign-off pending.

**Future work:** mentor-finalised paper; optional full-matrix human dual coding or Delphi if required; register expansion; tooling/MCP as a **separate** future project — out of scope here.

**Practical implication:** Healthtech teams using AI assistants should not treat CWE-only or OWASP-only review as sufficient for DPDP/ABDM logging and consent-architecture duties—those require obligation-specific assessment beyond the Bašić categories.
