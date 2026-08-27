# Obligation register — schema (normative)

This schema is the contract for Deliverable 1. Every row is one **observable, code-pattern-level criterion** derived from one regulatory unit (or an explicitly marked composite that will later be split). Follow `coding-protocol.md` when adding rows.

**Standing limits**
- We assess whether an implementation *exhibits a compliant pattern*. That is **necessary but not sufficient** for legal compliance.
- Never invent clause identifiers. If the local PDF page is not yet recorded, set `clause_id_verified` to `false` and leave `pdf_locus` as `VERIFY`.
- No rows keyed to WASA (see `logs/wasa-absence-finding.md`).

---

## Columns

| Column | Type | Definition |
|---|---|---|
| `obligation_id` | string | Stable ID: `OB-{INSTR}-{NNN}` e.g. `OB-DPDP-A-006`, `OB-DPDP-R-003`. Never reuse IDs; retire with status `superseded`. |
| `instrument` | enum | `DPDP_Act_2023` \| `DPDP_Rules_2025` \| `DPDP_Corrigendum_2025` \| `GSR_843E_2025` \| `ABDM_HDMP` \| `NRCeS_FHIR_IG` \| `OTHER_PUBLIC` |
| `source_id` | string | ID from `sources.md` (e.g. `R01`, `R03`, `R06`). |
| `source_version` | string | Exact stamp: gazette number, Act No., IG version, retrieval date. |
| `clause_id` | string | Section / rule / clause as printed in the source (e.g. `s.6(4)`, `r.3(b)(i)`). |
| `clause_id_verified` | bool | `true` only after a team member confirms the string against the **local** PDF. |
| `pdf_locus` | string | Local filename + page (or PDF bookmark). Use `VERIFY: <filename>` until checked. |
| `quoted_obligation` | text | Verbatim quote from the source. Ellipsis `…` only for omissions; never paraphrase inside this field. |
| `quote_confidence` | enum | `verbatim_from_retrieved_text` \| `needs_local_pdf_page_check` — if we used a retrieval extract rather than a team page-check, use the second. |
| `normative_force` | enum | `shall` \| `may` \| `shall_not` \| `definitional` \| `commencement` |
| `actor` | string | Who bears the duty (e.g. Data Fiduciary, Consent Manager, Significant Data Fiduciary). |
| `derived_criterion` | text | One observable criterion in our words: what must be *visible* in a patient-data module / described system for a reviewer to say the pattern is present. |
| `assessment_question` | text | Yes/partial/no question a rater answers using documentary evidence (design docs, audit report excerpts, code excerpts supplied by others — **we do not generate or run code**). |
| `evidence_required` | text | What the rater must cite (e.g. consent UI flow description; purpose→field mapping table; withdrawal path that disables tokens). |
| `taxonomy_dimensions` | list | Obligation-level dimensions this criterion feeds (see `taxonomy/dimension-definitions.md`): e.g. `consent_architecture`, `purpose_binding`, `withdrawal_propagation`, `breach_notification`, `retention_erasure`, `data_localization`, `abha_identity`, `consent_manager_mediation`, `fhir_conformance`, plus any Bašić category overlap. |
| `basic_categories_touch` | list | Optional pre-matrix hint only. **Not evidence.** Matrix cells are coded only under `mapping/cell-coding-rule.md` after that rule is FROZEN. Do not treat emptiness here as success. |
| `visibility_hypothesis` | enum | Prior belief only (not a result): `likely_fully_covered` \| `likely_partially_covered` \| `likely_not_visible`. Must not bias cell coding; hypotheses are sealed before dual coding or omitted. |
| `act_commencement_status` | string | Status of the **Act section** under G.S.R. 843(E). Until 843(E) is read: exactly `unverified — pending G.S.R. 843(E)`. Never leave blank (blank ≠ pending). Use `n/a — not an Act provision` when the row is Rules-only. |
| `act_commencement_basis` | string | Quote/locus in local `gsr-843e-…pdf` once read; else `unverified — pending G.S.R. 843(E)`. |
| `rule_commencement_status` | string | Status of the **Rule** under DPDP Rules r.1 (and corrigendum if it affects commencement text). Until confirmed against local Rules PDF: `unverified — pending Rules r.1 locus check` for Rules rows; `n/a — not a Rules provision` for Act-only rows. |
| `rule_commencement_basis` | string | Quote/locus in local Rules PDF (r.1(2)–(4) or as corrected); else pending string above. |
| `effective_from` | string | Derived only after **both** applicable mechanisms are verified. Until then: `unverified — pending G.S.R. 843(E)` (and Rules locus if Rules-linked). Never invent a calendar date. |
| `commencement_as_of` | date | Date relative to which verified statuses are stated (paper freeze date). |
| `healthcare_abdm_note` | text | Optional: how this general DPDP duty interacts with ABDM concepts **only when** an ABDM primary source is cited; otherwise `none_pending_ABDM_row`. |
| `scope_exclusion` | text | What this criterion does **not** claim (organizational DPO process, Board procedure, etc.). |
| `coding_status` | enum | `draft` \| `dual_coded` \| `reconciled` \| `frozen` \| `superseded` |
| `coder_a` / `coder_b` | string | Initials; keep both original codings in `logs/disagreement-record.md` when they differ. |
| `decision_log_ref` | string | Link to `logs/decision-log.md` entry for interpretive judgements. |
| `notes` | text | Open questions; corrigendum checks; etc. |

---

## Row atomicity rule

One row = one criterion. If a clause contains three separable observables (e.g. Rule 3(b)(i) itemised data **and** 3(b)(ii) purposes **and** 3(c) withdrawal link), create three rows that share the same `clause_id` parent prefix, or use `clause_id` with sub-letters and cross-reference in `notes`. Prefer split rows — GuideMe-style catalogues are built from fine-grained controls.

---

## Example rows (worked)

Quotes below are taken from retrieved Act/Rules text already in this project’s retrieval trail (Act gazette extract; Rules G.S.R. 846(E) text). **`clause_id_verified` stays false until you confirm against the local PDF page.** Do not treat these as frozen.

### Example 1 — purpose-limited consent (Act)

| Field | Value |
|---|---|
| `obligation_id` | `OB-DPDP-A-006-01` |
| `instrument` | `DPDP_Act_2023` |
| `source_id` | `R01` |
| `source_version` | Act No. 22 of 2023; gazette PDF `dpdp-act-2023-gazette-248045.pdf`; retrieved 2026-08-27 |
| `clause_id` | `s.6(1)` |
| `clause_id_verified` | **false** — confirm section labelling and page in local PDF |
| `pdf_locus` | `VERIFY: docs/regulatory/dpdp-act-2023-gazette-248045.pdf` |
| `quoted_obligation` | “The consent given by the Data Principal shall be free, specific, informed, unconditional and unambiguous with a clear affirmative action, and shall signify an agreement to the processing of her personal data for the specified purpose and be limited to such personal data as is necessary for such specified purpose.” |
| `quote_confidence` | `needs_local_pdf_page_check` |
| `normative_force` | `shall` |
| `actor` | Data Fiduciary (structuring the consent request); Data Principal (giving consent) |
| `derived_criterion` | For each processing operation on patient personal data, the implementation’s consent artifact binds that operation to a named specified purpose and does not request personal data fields outside what that purpose requires (purpose–field necessity). |
| `assessment_question` | Does the module’s consent/request path show purpose-specific agreement and omit non-necessary fields for that purpose? |
| `evidence_required` | Purpose list as presented to the user; field inventory collected at that step; mapping purpose → fields. |
| `taxonomy_dimensions` | `consent_architecture`, `purpose_binding` |
| `basic_categories_touch` | *(often none)* — may touch `sensitive_data_exposure` only if over-collection is framed as exposure; default **empty** until mapping justified |
| `visibility_hypothesis` | `likely_partial` |
| `commencement_status` | `phased_see_note` |
| `commencement_basis` | Act sections commence per G.S.R. 843(E) (`R05`); **fill exact section bucket after reading local 843(E) PDF** — do not invent which tranche contains s.6 |
| `commencement_as_of` | 2026-08-27 |
| `healthcare_abdm_note` | `none_pending_ABDM_row` (telemedicine illustration in the Act is illustrative only; not an ABDM API obligation) |
| `scope_exclusion` | Does not assess whether organizational consent policy was approved by a DPO; only whether the module pattern exhibits purpose-limited consent. |
| `coding_status` | `draft` |
| `notes` | Act illustration under s.6(1) (telemedicine app + contact list) is useful for rater training but is not itself a separate obligation row. |

### Example 2 — itemised notice content (Rules)

| Field | Value |
|---|---|
| `obligation_id` | `OB-DPDP-R-003-01` |
| `instrument` | `DPDP_Rules_2025` |
| `source_id` | `R03` |
| `source_version` | G.S.R. 846(E), 13 Nov 2025; local `gsr-846e-2025-11-13-dpdp-rules.pdf`; also check corrigendum `gsr-892e-2025-12-corrigendum-dpdp-rules.pdf` |
| `clause_id` | `r.3(b)(i)–(ii)` |
| `clause_id_verified` | **false** — confirm against local Rules PDF; check whether corrigendum alters this passage |
| `pdf_locus` | `VERIFY: docs/regulatory/gsr-846e-2025-11-13-dpdp-rules.pdf` (+ corrigendum pass) |
| `quoted_obligation` | “give, in clear and plain language, a fair account of the details necessary to enable the Data Principal to give specific and informed consent for the processing of her personal data, which shall include, at the minimum, — (i) an itemised description of such personal data; and (ii) the specified purpose or purposes of, and specific description of the goods or services to be provided or uses to be enabled by, such processing” |
| `quote_confidence` | `needs_local_pdf_page_check` |
| `normative_force` | `shall` |
| `actor` | Data Fiduciary |
| `derived_criterion` | The notice presented before/with consent lists personal data items individually (not only a blanket category) and states specified purpose(s) plus the goods/services/uses enabled. |
| `assessment_question` | Is there an itemised personal-data description and purpose/use description in the notice path for the patient-data module? |
| `evidence_required` | Notice text/screenshots or audit description of notice contents; checklist of items and purposes. |
| `taxonomy_dimensions` | `consent_architecture`, `purpose_binding` |
| `basic_categories_touch` | *(empty by default)* — CWE/OWASP categories do not express notice itemisation |
| `visibility_hypothesis` | `likely_not_visible` if only backend code is reviewed without notice copy; `likely_partial` if UI/notice artifacts are in scope of the case study |
| `commencement_status` | `not_yet_in_force` *(relative to Rules r.1(4) as retrieved)* |
| `commencement_basis` | Rules 2025, Rule 1(4): “Rules 3, 5 to 16, 22 and 23 shall come into force eighteen months after the date of publication of this Gazette.” Publication date 13 Nov 2025 ⇒ Rule 3 tranche is the +18-month set. **Confirm arithmetic/date on local PDF before freezing.** |
| `commencement_as_of` | 2026-08-27 |
| `healthcare_abdm_note` | `none_pending_ABDM_row` |
| `scope_exclusion` | Standalone-presentation requirement in r.3(a) is a **separate** row — not covered here. |
| `coding_status` | `draft` |
| `notes` | Prefer splitting into `…-01` itemisation and `…-02` purpose/goods if dual coding diverges. |

### Example 3 — withdrawal ease + cessation (Act; withdrawal propagation)

| Field | Value |
|---|---|
| `obligation_id` | `OB-DPDP-A-006-04` |
| `instrument` | `DPDP_Act_2023` |
| `source_id` | `R01` |
| `source_version` | Act No. 22 of 2023; `dpdp-act-2023-gazette-248045.pdf`; retrieved 2026-08-27 |
| `clause_id` | `s.6(4)` and linked duty in `s.6(6)` — **two atomic criteria should become two rows before freeze**; shown combined only to illustrate propagation |
| `clause_id_verified` | **false** |
| `pdf_locus` | `VERIFY: docs/regulatory/dpdp-act-2023-gazette-248045.pdf` |
| `quoted_obligation` | s.6(4): “Where consent given by the Data Principal is the basis of processing of personal data, such Data Principal shall have the right to withdraw her consent at any time, with the ease of doing so being comparable to the ease with which such consent was given.” s.6(6): “If a Data Principal withdraws her consent to the processing of personal data under sub-section (5), the Data Fiduciary shall, within a reasonable time, cease and cause its Data Processors to cease processing the personal data of such Data Principal unless such processing without her consent is required or authorised under the provisions of this Act or the rules made thereunder or any other law for the time being in force in India.” |
| `quote_confidence` | `needs_local_pdf_page_check` |
| `normative_force` | `shall` |
| `actor` | Data Fiduciary (and processors under its control) |
| `derived_criterion` | **(A)** Withdrawal control is available with effort comparable to giving consent. **(B)** On withdrawal, access/processing paths that depended on that consent stop within a defined handling path (including processor cessation), except documented lawful residual bases. |
| `assessment_question` | **(A)** Is withdrawal offered with comparable ease to consent grant? **(B)** Does withdrawal disable consent-based processing paths (tokens/sessions/jobs) rather than only updating a UI flag? |
| `evidence_required` | Consent vs withdrawal UX/steps; session/token invalidation or equivalent described in audit materials; processor instruction path if processors are in scope. |
| `taxonomy_dimensions` | `consent_architecture`, `withdrawal_propagation` |
| `basic_categories_touch` | May partially touch `authentication_authorization` (access continues after withdrawal) — matrix must justify; not automatic |
| `visibility_hypothesis` | `likely_partial` |
| `commencement_status` | `phased_see_note` |
| `commencement_basis` | **VERIFY** which G.S.R. 843(E) tranche includes s.6 before asserting in-force dates |
| `commencement_as_of` | 2026-08-27 |
| `healthcare_abdm_note` | Future ABDM row may link HIE-CM withdrawal mediation; **do not invent ABDM clause IDs here** |
| `scope_exclusion` | “Reasonable time” is not quantified in the quoted Act text; rubric anchors must not invent a numeric SLA. Residual processing under other law is out of pattern-scope unless evidenced. |
| `coding_status` | `draft` |
| `notes` | **Split before dual coding:** `OB-DPDP-A-006-04` (comparable ease) and `OB-DPDP-A-006-06` (cease processing). Combined row is for schema demonstration only. Rules r.3(c)(i) echoes comparable-ease withdrawal in the notice — cross-link, do not double-count without a decision-log entry. |

---

## Push-backs baked into this schema

1. **Matrix emptiness is an outcome, not a success criterion.** Cell labels follow `mapping/cell-coding-rule.md` only after freeze; Gap 1’s wording follows the counts.
2. **Act vs Rules commencement are separate columns.** Unverified cells must read `unverified — pending G.S.R. 843(E)` (or the Rules pending string), never blank.
3. **Example 3 must be split** before any reliability coding — combined rows inflate false agreement.
4. **No WASA-keyed rows.** WASA is an object of study (transparency finding). Re-source adjacent duties to OWASP Top 10, ABDM HDMP, CERT-In empanelment listings — each with its own `sources.md` ID.
