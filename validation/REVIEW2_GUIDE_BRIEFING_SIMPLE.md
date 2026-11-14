# Review 2 with your guide — simple version

**Who this is for:** You and your teammates, before meeting the guide alone.  
**What Review 2 is about:** Not a big panel pitch. She wants to know: *What have you done since Review 1? Does the method make sense? What do you need from me next?*

---

## 1. Where the project stands (say this in ~1 minute)

**In simple words:**  
We are building a **checklist-style research framework** (documents only — not an app). It helps answer:

> If someone only checks AI-written healthcare code for normal security bugs (like the usual CWE categories), **which Indian privacy/health-data rules would they actually notice — and which would they miss?**

**Done since Review 1**
- We fixed the rules for how we judge each mapping.
- We made a starter list of Indian legal duties (DPDP + ABDM).
- We filled a big comparison table (10 security categories × 17 legal duties = 170 cells).
- We found a clear main result: **access logging** is required by Indian rules, but the security categories don’t check whether logs exist.
- We drafted a scoring guide and a paper draft.

**Not done yet**
- A second *human* teammate should re-check the table (so results are trustworthy).
- Your guide should approve a few disputed cells.
- We still need a real hospital/health audit report for a case study.
- Expert panel (Delphi) only if she says we must.
- Final paper in *our* writing, not draft AI-assisted prose.

**One sentence for her:**  
*“The framework is built and we have a first result; we need your approval on a few judgements and clarity on what validation you want before we finish.”*

---

## 2. What to show her (keep it short)

1. The research question (security categories vs Indian rules).  
2. The five things we deliver (list, taxonomy, comparison table, scoring guide, validation write-up).  
3. The main finding: **logging gap**.  
4. Rough table result: most legal duties are “not visible” through security categories alone.  
5. Ask her for next steps (approval + case study + whether Delphi is needed).

**Tip:** Start with the logging finding. Don’t open with “kappa = 0.949” — that’s a side statistic.

---

## 3. Questions she may ask — simple answers

### About what the project is

**“What is your contribution?”**  
We’re making a clear, written method to compare normal security categories with Indian DPDP/ABDM duties, so teams can see what security review alone will miss.

**“Are you building software?”**  
No. This project is documents only — lists, mappings, scoring rules, and a report. No app, no scanner.

**“Does this mean legal compliance?”**  
No. We only check whether the *right patterns show up* in evidence. Real legal compliance also needs company process, people, and policy — not just what’s visible in a module review.

**“How is this different from OWASP / CWE?”**  
OWASP/CWE ask: “Is the code weak?”  
We ask: “If we only fix those weaknesses, which Indian legal duties become clear — and which stay invisible?”

---

### About the method

**“What are you comparing?”**  
Each cell in our table is: one security category × one legal duty.

**“What is RCM?”**  
Imagine the module was checked for that security category and all those issues were fixed to the normal standard. We ask: does that *guarantee* we can see the legal duty? That’s the RCM idea — don’t invent weird edge-case systems.

**“Why freeze the coding rule?”**  
So both people judging the table use the same written rules. No silent changing of definitions midway.

**“What is kappa / why is it high?”**  
Kappa is “how much do two reviewers agree?” Ours looks high partly because most cells are “not visible,” so agreement is easy. It does **not** mean the answers are automatically correct. Also, one reviewer pass was AI-assisted — so we still need a human re-check.

---

### About findings

**“What is your strongest result?”**  
**Logging.** Indian rules say you should be able to see who accessed personal data (logs / audit trail). The Bašić security categories don’t check whether those logs exist. In our table, that duty was “not visible” for all 10 categories (20 cells total). That is Gap 1.

**“Almost everything is not visible — did you fail?”**  
No. Empty cells are a *result*, not a failure. They support the claim that security categories and Indian legal duties are different languages. We also have one clear “fully covered” case (crypto category vs encryption requirement), so the method isn’t always empty.

**“Why no WASA?”**  
We couldn’t find a public official WASA document with citeable clause text. So we don’t invent WASA rows. We say that openly as a transparency problem, and use OWASP / ABDM / CERT-In where needed.

**“Is your legal list complete?”**  
No — it’s a starter set (MVP) covering the main families for this study. We are not claiming we covered every line of DPDP/ABDM.

---

### About progress and honesty

**“What did you finish after Review 1?”**  
Rules frozen, starter legal register, full comparison table, logging finding, scoring guide draft, paper draft.

**“Did AI help?”**  
Yes — for drafting and assistance. Legal quotes come from official PDFs we downloaded and page-checked. Final trust still needs human review and your approval.

**“What do you need from me?”**  
1. Approve (or correct) the few disputed table cells.  
2. Tell us if Delphi (expert survey) is required.  
3. Advise on getting a redacted audit report for case study.  
4. Feedback on paper format/voice.

**“What’s left before final?”**  
Human second reviewer, your approval, case study, Delphi only if required, final paper polish.

---

### Harder questions

**“Isn’t ‘law ≠ CWE’ obvious?”**  
The point isn’t just saying it — it’s building a **usable written instrument** that measures the gap cell by cell, with a concrete Indian example (logging) checked against the paper and the law texts.

**“Couldn’t someone force ‘not visible’ everywhere?”**  
Our rules stop that. You must argue from the category’s normal checklist, not from “maybe some weird system exists.” We also tested a common mistake: treating CWE-117 as if it means “logging is covered” (it doesn’t — it assumes logs already exist).

**“Why no coding product for a CS project?”**  
Design-science research can deliver a designed method + evaluation, not only software. Our mentor constraint is documents-only. Building a scanner would be a different project.

**“Is the law even in force yet?”**  
Many duties start later (around **13 May 2027** under the commencement notice). We still study the patterns now, and we record the dates in the register.

---

## 4. Ask her these three things before you leave

1. Please approve our reconciliation of the disputed cells (or tell us what to change).  
2. For finishing: is human double-checking + one case study enough, or do we also need Delphi?  
3. What should be ready before the next / final review?

---

## 5. Opening you can actually say

> “After Review 1, we locked our coding rules, built a starter DPDP/ABDM duty list, and filled the comparison table. Our main finding is that access-logging duties required by Indian rules are not visible under any of the ten security categories we used. For Review 2, we want your approval on a few disputed judgements and clear guidance on what validation you want before final submission.”

---

## 6. Do / don’t

| Do | Don’t |
|---|---|
| Lead with the logging gap | Lead with kappa as “proof we are right” |
| Say “patterns, not legal compliance” | Say “we ensure DPDP compliance” |
| Admit human re-check is still pending | Hide that AI helped with drafting/coding assistance |
| Ask for clear next steps | Promise Delphi/case study with no plan |
| Cite Bašić version 4, 21 studies | Mix versions or say “about 20 studies” |

---

*Full technical version (same content, more formal): `REVIEW2_GUIDE_BRIEFING.md`*
