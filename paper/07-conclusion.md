# Conclusion

**Status:** draft — team rewrite.

We presented a documentary framework for assessing whether patient-data modules exhibit patterns consistent with selected DPDP and ABDM obligations when reviewers use Bašić and Giaretta’s ten CWE-shaped vulnerability categories. The cross-mapping matrix, dual-coded under a frozen counterfactual rule, shows that most regulatory observables in our MVP register are **not visible** through category remediation alone (156/170 cells `not_visible`). The strongest structural instance is **access-logging demonstrability**: Indian rules require visibility of personal-data access, yet Bašić v4’s 21-study taxonomy includes no category that assesses log existence—confirmed across twenty matrix cells and PDF-verified absence of logging CWEs.

We extended the taxonomy with obligation-level dimensions, supplied an assessment rubric for documentary evidence, and documented the lack of a public WASA specification as a transparency finding rather than inventing register rows. Inter-rater κ was high but must be interpreted cautiously: agreement on emptiness is not agreement on legal compliance, and agent-assisted coding awaits human replication.

**Limitations:** MVP register scope; pattern assessment only; commencement dates largely 2027-05-13 for substantive duties; Delphi and case study not yet executed.

**Future work (team):** human second coder; expert Delphi; case study on an existing audit report; register expansion; mentor-finalised paper.

**Practical implication:** Healthtech teams using AI assistants should not treat CWE-only or OWASP-only review as sufficient for DPDP/ABDM logging and consent-architecture duties—those require obligation-specific assessment beyond the Bašić categories.
