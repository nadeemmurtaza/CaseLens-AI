# CaseLens AI

## Risks, Assumptions and Decisions Register

### Document Control

**Project:** CaseLens AI  
**Document:** Risks, Assumptions and Decisions Register  
**Version:** 1.0  
**Status:** Active  
**Date:** 18 July 2026  
**Review Frequency:** At every phase gate and before submission  

---

## 1. Purpose

This register keeps material uncertainty visible.

It records:

- Risks that may prevent completion or reduce quality
- Assumptions that remain unproven
- Decisions that are intentionally locked
- Dependencies outside the codebase
- Issues that require later review

The project must not quietly convert assumptions into facts or deferred features into promises. That habit is how small student apps acquire enterprise roadmaps and no working submit button.

---

## 2. Status Definitions

### Risk Status

- `Open`
- `Mitigated`
- `Accepted`
- `Occurred`
- `Closed`

### Assumption Status

- `Unverified`
- `Supported`
- `Disproved`
- `Superseded`

### Decision Status

- `Proposed`
- `Approved`
- `Superseded`

### Severity

- `Critical`: Can prevent submission or expose serious safety/security failure
- `High`: Can prevent a mandatory feature from working
- `Medium`: Can materially reduce quality, usability, or marks
- `Low`: Limited impact or easily corrected

---

## 3. Risk Register

### RISK-01: Scope Expansion

**Severity:** Critical  
**Status:** Open  
**Description:** The project may expand into an LMS, patient system, broad question bank, native mobile app, or medical-image platform.  
**Impact:** Mandatory features remain incomplete before the deadline.  
**Mitigation:** Enforce P0 scope and out-of-scope list. Every new feature must trace to an assignment requirement or replace a weaker feature.  
**Trigger:** A proposed feature requires authentication, cloud database design, complex roles, image processing, or new external services.  
**Owner:** Project owner  

---

### RISK-02: Generic Chatbot Appearance

**Severity:** High  
**Status:** Open  
**Description:** The application may look like a generic text box connected to Gemini.  
**Impact:** Weak originality score.  
**Mitigation:** Use a structured case workspace, controlled output sections, MCQ practice, local revision history, and clear comparison in README.  
**Evidence:** User Flows, AI Specification, final screenshots.  

---

### RISK-03: Unsafe Medical Output

**Severity:** Critical  
**Status:** Open  
**Description:** The model may provide unjustified certainty, patient-specific treatment, or unsafe advice.  
**Impact:** Safety failure and loss of credibility.  
**Mitigation:** Educational system prompt, structured schema, explicit uncertainty, output validation, safety test cases, visible disclaimers.  
**Trigger:** Output contains prescriptions, doses, confirmed-diagnosis language without support, or emergency-management instructions for a real person.  

---

### RISK-04: Invented Clinical Facts

**Severity:** High  
**Status:** Open  
**Description:** Gemini may invent absent findings, laboratory values, imaging, or patient history.  
**Impact:** Incorrect educational output.  
**Mitigation:** Separate supplied facts from inference, prohibit treating unmentioned findings as absent, test ambiguous and sparse cases.  

---

### RISK-05: Prompt Injection

**Severity:** High  
**Status:** Open  
**Description:** Case text may contain instructions asking the model to ignore rules or reveal prompts.  
**Impact:** Format, safety, or confidentiality failure.  
**Mitigation:** Treat case text as untrusted data, delimit it, use system rules, validate output, and include prompt-injection test cases.  

---

### RISK-06: Invalid Provider Output

**Severity:** High  
**Status:** Open  
**Description:** Gemini may return malformed JSON or incomplete fields.  
**Impact:** Broken results page or misleading output.  
**Mitigation:** Strict schema validation, bounded schema-repair retry, useful public error, never render unvalidated output.  

---

### RISK-07: Gemini API Availability

**Severity:** High  
**Status:** Open  
**Description:** Provider errors, quotas, rate limits, or timeouts may disrupt the primary workflow.  
**Impact:** AI feature fails during evaluation.  
**Mitigation:** Validate credentials early, implement timeouts and clear errors, avoid uncontrolled retries, test production before submission.  
**Dependency:** Working Gemini API access and quota.  

---

### RISK-08: API Key Exposure

**Severity:** Critical  
**Status:** Open  
**Description:** A real Gemini key may enter client code, screenshots, commits, or README.  
**Impact:** Credential compromise and public-repository failure.  
**Mitigation:** Server-only environment variable, `.gitignore`, placeholder `.env.example`, secret scan, repository-history review.  

---

### RISK-09: Real Patient Information Entered

**Severity:** Critical  
**Status:** Open  
**Description:** A user may paste identifiable patient information.  
**Impact:** Privacy and ethical risk.  
**Mitigation:** Prominent warning, no identity fields, avoid ordinary logging of case text, privacy reminder in output, local-only history, test obvious identifier patterns where practical.  
**Residual risk:** Automated detection cannot guarantee identification of all personal information.  

---

### RISK-10: Local Storage Misunderstood as Secure Clinical Storage

**Severity:** Medium  
**Status:** Open  
**Description:** Users may assume recent cases are protected cloud records.  
**Impact:** Unsafe use on shared devices.  
**Mitigation:** Explain local-device storage, provide delete and clear-all actions, prohibit real patient data, avoid security claims.  

---

### RISK-11: Local Storage Failure or Corruption

**Severity:** Medium  
**Status:** Open  
**Description:** Browser settings, quota, private mode, or invalid data may prevent local history.  
**Impact:** Cases cannot be saved or reopened.  
**Mitigation:** Treat stored data as untrusted, version records, fail gracefully, keep AI workflow usable, never claim save success falsely.  

---

### RISK-12: Weak MCQ Quality

**Severity:** High  
**Status:** Open  
**Description:** Questions may be ambiguous, have multiple correct answers, or rely on invented facts.  
**Impact:** Reduced educational value and originality.  
**Mitigation:** Structured MCQ schema, one-best-answer rule, fixed four options, validation, sample review, prompt-quality tests.  

---

### RISK-13: Overly Long AI Responses

**Severity:** Medium  
**Status:** Open  
**Description:** Generated analysis may be verbose and difficult to study on mobile.  
**Impact:** Poor usability and increased latency/cost.  
**Mitigation:** Concise prompt rules, response-size limits, grouped sections, progressive disclosure.  

---

### RISK-14: Mobile Layout Failure

**Severity:** High  
**Status:** Open  
**Description:** Long medical content, options, and controls may overflow or become difficult to use.  
**Impact:** Completion and deployment quality failure.  
**Mitigation:** Mobile-first layouts, 320px testing, wrapping rules, touch targets, no fixed-width result panels.  

---

### RISK-15: Accessibility Gaps

**Severity:** Medium  
**Status:** Open  
**Description:** Generated content, loading states, errors, or MCQ interactions may be inaccessible.  
**Impact:** Reduced quality and usability.  
**Mitigation:** Semantic structure, visible labels, keyboard access, focus management, announcements, contrast review, automated and manual tests.  

---

### RISK-16: Deployment Works Locally but Fails on Vercel

**Severity:** Critical  
**Status:** Open  
**Description:** Environment variables, server routes, runtime differences, or build errors may break production.  
**Impact:** Mandatory deployment criterion fails.  
**Mitigation:** Deploy early, test the real production route, pin supported runtime, verify environment configuration, retest final commit.  

---

### RISK-17: README Written Too Late

**Severity:** High  
**Status:** Open  
**Description:** Reporting may be rushed after development.  
**Impact:** Marks lost despite working application.  
**Mitigation:** Maintain README structure throughout development, capture screenshots and decisions continuously, run NotebookLM gap audit.  

---

### RISK-18: Repository Is Public but Incomplete

**Severity:** High  
**Status:** Open  
**Description:** The submitted repository may omit latest code, setup steps, or live URL.  
**Impact:** Evaluator cannot reproduce or understand the project.  
**Mitigation:** Final repository audit, compare deployment commit to repository, verify anonymous access.  

---

### RISK-19: Full Portal Brief Adds Requirements

**Severity:** High  
**Status:** Open  
**Description:** The detailed portal brief may contain requirements absent from the announcement.  
**Impact:** Current baseline may be incomplete.  
**Mitigation:** Obtain and upload the full brief as early as possible, rerun compliance and traceability review, record changes.  
**Blocker:** Full portal brief not supplied.  

---

### RISK-20: Deadline Compression

**Severity:** Critical  
**Status:** Open  
**Description:** The deadline is fixed at 27 July 2026, 11:59 PM PKT.  
**Impact:** Late submission or incomplete app.  
**Mitigation:** Prioritize P0 loop, deploy before final day, freeze scope, reserve final period for verification and README.  

---

## 4. Assumptions Register

### ASM-01: Web Application Is Acceptable

**Status:** Supported  
**Basis:** The assignment requires a public URL and mentions Vercel deployment instruction.  
**Consequence if false:** Delivery format may need revision.  

### ASM-02: Next.js Is Permitted

**Status:** Supported  
**Basis:** Students may use any tools.  
**Consequence if false:** Rebuild risk.  

### ASM-03: Gemini API Is Permitted

**Status:** Supported  
**Basis:** Assignment requires an AI feature and permits any tools.  
**Consequence if false:** AI provider replacement.  

### ASM-04: No Database Is Mandatory

**Status:** Unverified  
**Basis:** No database requirement appears in the supplied announcement.  
**Safeguard:** Use local storage for MVP and revise if portal brief says otherwise.  

### ASM-05: Authentication Is Not Mandatory

**Status:** Unverified  
**Basis:** No authentication requirement appears in supplied announcement.  
**Safeguard:** Keep it out of MVP unless an official source requires it.  

### ASM-06: Individual Project

**Status:** Unverified  
**Basis:** Announcement addresses students but does not explicitly state team rules.  
**Safeguard:** README must accurately identify contributors.  

### ASM-07: Repository Must Remain Public During Evaluation

**Status:** Supported  
**Basis:** Public GitHub repository is mandatory and is the submitted item.  

### ASM-08: Vercel Public URL Is Sufficient

**Status:** Supported  
**Basis:** Announcement specifically says GitHub and Vercel deployment will be taught.  

### ASM-09: Browser Print Is Acceptable

**Status:** Unverified  
**Basis:** PDF generation is not an assignment requirement.  
**Safeguard:** Implement reliable print styles rather than server PDF complexity.  

### ASM-10: Local History Is Optional but Valuable

**Status:** Supported  
**Basis:** It strengthens completion without requiring accounts or cloud storage.  

### ASM-11: Examination Labels May Be Used Descriptively

**Status:** Unverified  
**Basis:** NRE, USMLE, PLAB, and MRCP styles are product configuration, not official affiliations.  
**Safeguard:** Add non-affiliation language.  

### ASM-12: Provider Structured Output Is Available or Emulatable

**Status:** Unverified  
**Basis:** Exact Gemini model and SDK will be selected later.  
**Safeguard:** Enforce server-side schema validation regardless of provider support.  

---

## 5. Decision Register

### DEC-01: Product Category

**Status:** Approved  
**Decision:** CaseLens AI is an AI-powered medical-learning web application.  
**Reason:** Matches public URL deployment and interactive app requirements.  

### DEC-02: Primary User

**Status:** Approved  
**Decision:** Medical learners and examination candidates are the primary users.  

### DEC-03: Core Problem

**Status:** Approved  
**Decision:** The product addresses unstructured clinical-case reasoning and weak conversion of cases into active revision.  

### DEC-04: Core Learning Loop

**Status:** Approved  
**Decision:** Case input → structured analysis → MCQ practice → copy/print/local revisit.  

### DEC-05: AI Provider

**Status:** Approved  
**Decision:** Use Gemini API for live analysis and MCQ generation.  

### DEC-06: Application Framework

**Status:** Approved for planning  
**Decision:** Use Next.js with TypeScript and Tailwind CSS.  
**Review condition:** Confirm current supported versions and deployment compatibility during architecture phase.  

### DEC-07: Server-Side AI Calls

**Status:** Approved  
**Decision:** Gemini requests must run through protected server-side routes.  

### DEC-08: Structured Responses

**Status:** Approved  
**Decision:** AI output must pass strict JSON schema validation before display.  

### DEC-09: Local-Only History

**Status:** Approved  
**Decision:** Store recent cases in browser local storage for the MVP.  
**Reason:** Supports revision without authentication or cloud database risk.  

### DEC-10: No Accounts in MVP

**Status:** Approved  
**Decision:** Authentication and user accounts are excluded.  

### DEC-11: Educational Boundary

**Status:** Approved  
**Decision:** The application is not for real-patient diagnosis, treatment, or emergency management.  

### DEC-12: Public Repository

**Status:** Approved  
**Decision:** Use `nadeemmurtaza/CaseLens-AI` as the public source repository.  

### DEC-13: Deployment

**Status:** Approved  
**Decision:** Deploy the application publicly on Vercel.  

### DEC-14: Design Tool Boundary

**Status:** Approved  
**Decision:** Google Stitch may generate design references but does not define product behavior.  

### DEC-15: NotebookLM Boundary

**Status:** Approved  
**Decision:** NotebookLM is the private evidence and audit workspace, not a production feature.  

### DEC-16: README as Project Report

**Status:** Approved  
**Decision:** The repository README is a graded primary deliverable and must link to the live app.  

### DEC-17: Out-of-Scope Features

**Status:** Approved  
**Decision:** Exclude LMS features, cloud history, native apps, payments, image diagnosis, voice consultation, and multi-provider AI routing from MVP.  

### DEC-18: Pull-Request Workflow

**Status:** Approved  
**Decision:** Meaningful changes use branches and reviewable pull requests after repository initialization.  

---

## 6. Dependencies Register

| Dependency ID | Dependency | Required for | Status | Failure impact |
|---|---|---|---|---|
| DEP-01 | Full portal assignment brief | Final requirement baseline | Unavailable | Possible missing requirements |
| DEP-02 | Gemini API account and key | AI feature | Not verified | Primary feature blocked |
| DEP-03 | Gemini quota and supported model | Production AI requests | Not verified | Reliability risk |
| DEP-04 | GitHub repository access | Source and submission | Available | Submission blocked if lost |
| DEP-05 | Vercel account and project access | Live deployment | Not verified | Deployment blocked |
| DEP-06 | NotebookLM access | Evidence audits | Not verified | Audits must be done manually |
| DEP-07 | Google Stitch access | Design exploration | Not verified | Design can proceed through alternatives |
| DEP-08 | Representative mobile browser | Mobile verification | Not verified | Production quality unproven |

---

## 7. Change-Control Rule

A change requires entry in this register when it affects:

- Assignment compliance
- MVP scope
- AI provider or model behavior
- Response schema
- Safety boundary
- User journeys
- Data storage
- Repository visibility
- Deployment target
- Deadline plan
- README reporting commitments

Each material change must state:

- What changed
- Why
- Which documents are affected
- Which tests must change
- Whether approval is required

---

## 8. Phase Gate Review

At the end of each phase:

1. Review every open Critical and High risk.
2. Update assumptions with new evidence.
3. Record new architecture or product decisions.
4. Close risks only with evidence.
5. Confirm no hidden dependency has become critical.
6. Update the final submission risk.

---

## 9. Current Summary

**Critical open risks:** Scope, medical safety, secret exposure, deployment, deadline, unknown portal requirements  
**Highest unresolved dependency:** Full portal assignment brief  
**MVP decisions recorded:** Yes  
**Implementation risks verified:** Not yet  
**Register status:** Active
