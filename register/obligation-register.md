# Obligation register — minimum viable set (pilot corpus)

**Register version:** `register-v0.2-mvp-2026-08-27`  
**Purpose:** ~dozen criteria spanning families for the **pilot**, not the final catalogue.  
**Quote confidence:** extracted from local PDFs / prior verified extracts; set `clause_id_verified` after human page-stamp.  
**Commencement:** filled from `commencement-lookup.md` (843(E) + Rules r.1).

Compact view. Full field sets can be expanded row-by-row during dual coding of the register itself.

| obligation_id | family | instrument | clause_id | derived_criterion (short) | assessment_question (short) | act_commencement_status | rule_commencement_status | effective_from | taxonomy_dimensions |
|---|---|---|---|---|---|---|---|---|---|
| OB-DPDP-A-006-01 | consent | Act | s.6(1) | Consent is purpose-specific and limited to personal data necessary for that purpose | Does consent bind processing to a named purpose without non-necessary fields? | +18m (843(E)(c)): s.6(1) → **not_yet; effective 2027-05-13** | n/a | **2027-05-13** | consent_architecture, purpose_binding |
| OB-DPDP-A-006-04 | consent | Act | s.6(4) | Withdrawal available with ease comparable to grant | Is withdrawal effort comparable to consent grant? | +18m → **2027-05-13** | n/a | **2027-05-13** | consent_architecture, withdrawal_propagation |
| OB-DPDP-A-006-06 | consent | Act | s.6(6) | On withdrawal, fiduciary ceases (and causes processors to cease) consent-based processing except other lawful authority | Does withdrawal stop consent-based processing paths (incl. processors)? | +18m → **2027-05-13** | n/a | **2027-05-13** | withdrawal_propagation |
| OB-DPDP-R-003-01 | consent / notice | Rules | r.3(b)(i) | Notice includes itemised description of personal data | Is personal data itemised in the notice? | n/a | +18m (r.1(4)) → **2027-05-13** | **2027-05-13** | consent_architecture |
| OB-DPDP-R-003-02 | consent / notice | Rules | r.3(b)(ii) | Notice states specified purpose(s) and goods/services/uses enabled | Are purposes and enabled uses described in the notice? | n/a | +18m → **2027-05-13** | **2027-05-13** | purpose_binding |
| OB-DPDP-R-003-03 | consent / notice | Rules | r.3(c)(i) | Notice gives means to withdraw with comparable ease | Does notice path expose comparable-ease withdrawal means? | n/a | +18m → **2027-05-13** | **2027-05-13** | withdrawal_propagation |
| OB-DPDP-A-008-05 | security | Act | s.8(5) | Reasonable security safeguards to prevent personal data breach | Are reasonable security safeguards present for personal data held/controlled? | +18m (ss.7–10) → **2027-05-13** | n/a | **2027-05-13** | *(technical overlap possible)* |
| OB-DPDP-R-006-01 | security | Rules | r.6(1)(a) | Minimum safeguard: encryption/obfuscation/masking/virtual tokens for personal data | Is personal data protected by one of the listed technical measures? | n/a | +18m → **2027-05-13** | **2027-05-13** | |
| OB-DPDP-R-006-02 | security | Rules | r.6(1)(c) | Visibility of access via logs/monitoring/review for unauthorized access detection | Are access logs/monitoring present for personal-data access? | n/a | +18m → **2027-05-13** | **2027-05-13** | |
| OB-DPDP-A-008-06 | breach | Act | s.8(6) | On personal data breach, intimate Board and each affected Data Principal as prescribed | Is there a path to intimate Board and affected principals on breach? | +18m → **2027-05-13** | n/a | **2027-05-13** | breach_notification |
| OB-DPDP-R-007-01 | breach | Rules | r.7(1) | Without delay, intimate each affected principal with prescribed content elements | Does principal-facing breach intimation cover nature/extent/timing, consequences, mitigations, safety steps, contact? | n/a | +18m → **2027-05-13** | **2027-05-13** | breach_notification |
| OB-DPDP-R-007-02 | breach | Rules | r.7(2) | Intimate Board without delay (summary) and within 72 hours (detailed) | Are Board intimation timelines/content paths defined? | n/a | +18m → **2027-05-13** | **2027-05-13** | breach_notification |
| OB-DPDP-A-008-07 | retention | Act | s.8(7) | Erase when consent withdrawn or purpose no longer served (unless law requires retention); cause processors to erase | Is there an erasure path tied to withdrawal/purpose-end (with legal-retention exception)? | +18m → **2027-05-13** | n/a | **2027-05-13** | retention_erasure |
| OB-DPDP-A-016-01 | localization | Act | s.16(1) | Transfers restricted to countries/territories as Central Government may notify | Does outbound transfer logic respect notified restriction list mechanism? | +18m (ss.11–17) → **2027-05-13** | n/a | **2027-05-13** | data_localization |
| OB-ABDM-HDMP-16-04 | ABDM identity | ABDM_HDMP | cl.16.4 | No denial of health facility/service merely for lacking/not disclosing Health ID / non-participation | Can care proceed without requiring Health ID creation/disclosure? | n/a (policy) | n/a | **policy — see HDMP; not under 843(E)** | abha_identity |

### Quoted obligations (verbatim anchors)

**OB-DPDP-A-006-01** — Act s.6(1): “The consent given by the Data Principal shall be free, specific, informed, unconditional and unambiguous with a clear affirmative action, and shall signify an agreement to the processing of her personal data for the specified purpose and be limited to such personal data as is necessary for such specified purpose.”

**OB-DPDP-A-006-04** — Act s.6(4): “…right to withdraw her consent at any time, with the ease of doing so being comparable to the ease with which such consent was given.”

**OB-DPDP-A-006-06** — Act s.6(6): “…the Data Fiduciary shall, within a reasonable time, cease and cause its Data Processors to cease processing… unless such processing without her consent is required or authorised…”

**OB-DPDP-R-003-01/02** — Rules r.3(b): itemised personal data; specified purpose(s) and goods/services/uses (see local Rules PDF).

**OB-DPDP-R-003-03** — Rules r.3(c)(i): withdraw with comparable ease (see local Rules PDF).

**OB-DPDP-A-008-05** — Act s.8(5): “…taking reasonable security safeguards to prevent personal data breach.”

**OB-DPDP-R-006-01/02** — Rules r.6(1)(a),(c) (see local Rules PDF).

**OB-DPDP-A-008-06** — Act s.8(6): intimate Board and each affected Data Principal as prescribed.

**OB-DPDP-R-007-01/02** — Rules r.7(1)–(2) (see local Rules PDF).

**OB-DPDP-A-008-07** — Act s.8(7): erase on withdrawal or when purpose no longer served (unless law requires retention); cause processor erasure.

**OB-DPDP-A-016-01** — Act s.16(1): Central Government may restrict transfer to notified country/territory.

**OB-ABDM-HDMP-16-04** — HDMP cl.16.4: “No individual shall be denied access to any health facility or service… merely by reason of not creating a Health ID or disclosing their Health ID… or for not being in possession of a Health ID, or for not choosing to participate in the NDHE.”

### Page-verify checklist

Every row: open local PDF → stamp `pdf_locus` → set `clause_id_verified=true`. Rules rows: corrigendum pass.
