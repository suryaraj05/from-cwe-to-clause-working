# Paper summaries (from our project docs)

**Purpose:** Quick reference for Review 2 / guide questions.  
**Rule:** Summaries reflect what *our project uses* from each source (`sources.md`, related-work, findings).  
**Cite Bašić only as arXiv:2412.15004v4** (21 studies — do not say “~20”).

---

## A. Base / core papers

### P01 — Bašić & Giaretta (arXiv v4)  
**Full idea:** Systematic literature review of security issues in LLM-generated code.  
**What it does:** Groups findings from **21 studies** into **ten vulnerability categories**, mapped mainly to **CWE**.  
**Categories (our rows):** Injection, Memory Management, File Management, Deserialization, Sensitive Data Exposure, Authentication & Authorization, Cryptography, Resource Management, Coding Standards, Error Handling.  
**Why we use it:** This is our **matrix row vocabulary** — the “security lens.”  
**Limitation for us:** Jurisdiction-agnostic. No DPDP/ABDM. No category that assesses whether **access/audit logs exist** (Gap 1).  
**Say to guide:** “This is our technical taxonomy. We pin v4 because earlier versions differed on study count.”

---

### P02 — (In)Security of Vibe-Coded Applications (arXiv 2606.23130, 2026)  
**Full idea:** Recent preprint on security problems when apps are built in a “vibe coding” / heavy AI-assisted style.  
**Why we use it:** **Recent** evidence that AI-assisted development creates new insecurity patterns.  
**Limitation:** Preprint — treat as supporting motivation, not settled doctrine.  
**Say to guide:** “A recent paper showing AI-coded apps still have serious security issues.”

---

### P03 — Ayala-Rivera & Pasquale — GuideMe (IEEE RE 2018)  
**Full idea:** Method to turn **GDPR** text into concrete privacy controls (operationalise regulation).  
**Why we use it:** Method model for our **obligation register** — quote law → atomic criterion → assessment question → evidence.  
**Limitation:** GDPR + human-authored requirements; **not** DPDP, **not** ABDM, **not** AI-generated code assessment.  
**Say to guide:** “GuideMe shows how to extract controls from law. We adapt that idea to Indian DPDP/ABDM.”

---

## B. Method papers (these can look “old” — that is normal)

### P04 — Nickerson, Varshney & Muntermann (2013)  
**Full idea:** How to build a good taxonomy in information systems; gives **ending conditions** (8 objective + 5 subjective).  
**Why we use it:** To justify our **extended taxonomy** (adding legal dimensions beyond CWE) and to check when the taxonomy is “good enough.”  
**Say to guide:** “Classic taxonomy method — we use it for structure, not as a 2013 topic paper.”

---

### P05 — Hevner et al. (MISQ 2004)  
**Full idea:** **Design science** — research can contribute by building an **artefact** and evaluating it rigorously (not only by building commercial software).  
**Why we use it:** Frames our whole project: framework (artefact) + dual coding / coverage / planned case study & Delphi (evaluation).  
**Say to guide:** “This justifies documents-only design-science work as valid research.”

---

### P06 — Kundisch et al. (2022)  
**Full idea:** Updated guidance for people designing taxonomies.  
**Why we use it:** Supports amendment rules / good taxonomy practice alongside Nickerson.  
**Say to guide:** “More recent taxonomy-design guidance; secondary to Nickerson for us.”

---

## C. Supporting empirical papers (AI code insecurity)

### P07 — Pearce et al. — “Asleep at the Keyboard?” (IEEE S&P 2022)  
**Full idea:** Evaluates security of code from GitHub Copilot.  
**Key figure in our docs:** Roughly **~40% insecure** across large scenario set (1,689 programs / 89 scenarios).  
**Why we use it:** Strong early evidence that AI assistants produce vulnerable code.  
**Limitation:** Technical security only — no Indian regulation.  
**Say to guide:** “Shows Copilot often suggests insecure code — motivation for our problem.”

---

### P08 — Perry et al. (CCS 2023)  
**Full idea:** Studies whether users write **more insecure code** when using AI assistants.  
**Why we use it:** Shows the human+AI workflow can worsen security outcomes.  
**Limitation:** Again technical / behavioural — not DPDP/ABDM.  
**Say to guide:** “Recent empirical work: AI assistance can lead people to ship less secure code.”

---

### P09 — SafeGenBench (arXiv 2025)  
**Full idea:** Benchmark for whether models generate secure code.  
**Key figures in our docs:** 558 cases; 8 vuln categories; 13 models; ~**37%** average zero-shot accuracy.  
**Why we use it:** **Recent** evidence models still fail security tasks often.  
**Limitation:** Benchmark categories ≠ Indian legal duties.  
**Say to guide:** “2025 benchmark — models still struggle to generate secure code.”

---

### P10 — GoodVibe (arXiv 2026)  
**Full idea:** Optional related work on “security-by-vibe” ideas for LLM code generation.  
**Why we use it:** Optional recent related work; not a load-bearing method source.  
**Say to guide:** “Optional recent related work — not central to our method.”

---

## D. How the papers fit together (one paragraph for guide)

> Pearce, Perry, SafeGenBench, vibe-coded, and GoodVibe show **AI-generated code is often insecure**.  
> Bašić organises that insecurity into **ten CWE categories** (our rows).  
> GuideMe shows how to turn **law into assessable controls** (our register method).  
> Hevner + Nickerson (+ Kundisch) tell us **how to build and justify** a research artefact/taxonomy.  
> **None** of these give DPDP/ABDM visibility for AI-generated healthcare code — that gap is our contribution, using Indian primary sources (Act, Rules, ABDM HDMP, FHIR IG).

---

## E. Not papers, but she may ask — primary Indian sources

| ID | What it is | Role in project |
|---|---|---|
| **DPDP Act 2023** | Main data-protection law | Consent, security, breach, retention, transfer duties |
| **DPDP Rules 2025** | Detailed rules (G.S.R. 846(E)) | Notice, safeguards, logging r.6(1)(c), breach timelines |
| **G.S.R. 843(E)** | Commencement notice | When sections start (many +18m → 2027-05-13) |
| **G.S.R. 892(E)** | Corrigendum | Clerical fixes to Rules |
| **ABDM HDMP** | Health data management policy | Health ID, audit trail 27.5(a), etc. |
| **NRCeS FHIR IG v6.5.0** | Health data exchange profiles | FHIR conformance row |
| **OWASP / CWE / CERT-In** | Security standards / auditor listing | Re-sourcing when WASA has no public official spec |
| **WASA** | *Not found* as public official spec | Object of study / transparency finding — **no register rows** |

---

## F. 20-second answer if she asks “summarise your papers”

> “Our base paper Bašić v4 gives ten CWE categories from 21 studies. GuideMe teaches extracting controls from regulation. Hevner and Nickerson are our research-method base. Recent papers — Pearce, Perry, SafeGenBench, and 2026 AI-coding security preprints — show AI code insecurity is still current. We then map that technical lens to recent Indian law: DPDP 2023/2025 and ABDM.”
