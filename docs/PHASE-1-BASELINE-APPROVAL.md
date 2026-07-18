# CaseLens AI

## Phase 1 Baseline Approval Record

### Document Control

**Project:** CaseLens AI  
**Document:** Phase 1 Baseline Approval Record  
**Version:** 1.0  
**Status:** Baseline Prepared — Executive Approval Pending  
**Date:** 18 July 2026  
**Submission Deadline:** Monday, 27 July 2026, 11:59 PM PKT  

---

## 1. Purpose

This record identifies the documents, decisions, conditions, and unresolved exceptions that define the CaseLens AI Phase 1 baseline.

It prevents later phases from changing the product casually or claiming that planning documents prove implementation.

Phase 1 approval authorizes design and technical planning against the baseline. It does not prove that application code exists, tests pass, Gemini works, Vercel is configured, or the assignment is ready for submission.

---

## 2. Phase 1 Objective

Phase 1 establishes:

- The confirmed assignment requirements
- The project purpose and target users
- The original problem and product response
- The MVP boundary
- Exact product behavior
- Application routes and user journeys
- AI responsibilities, prompts, schemas, and safeguards
- Assignment traceability
- NotebookLM evidence workflow
- Risks, assumptions, dependencies, and decisions
- Approval and change-control rules

---

## 3. Baseline Document Set

| # | Document | Repository path | Status at baseline preparation |
|---|---|---|---|
| 1 | Assignment Requirements Source Record | `docs/ASSIGNMENT-REQUIREMENTS-SOURCE-RECORD.md` | Source baseline |
| 2 | Project Charter | `docs/PROJECT-CHARTER.md` | Approved baseline document |
| 3 | Product Requirements Document | `docs/PRODUCT-REQUIREMENTS.md` | Proposed for approval |
| 4 | Assignment Traceability Matrix | `docs/ASSIGNMENT-TRACEABILITY-MATRIX.md` | Proposed for approval |
| 5 | User Flows and Information Architecture | `docs/USER-FLOWS-AND-INFORMATION-ARCHITECTURE.md` | Proposed for approval |
| 6 | AI Feature and Prompt Specification | `docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md` | Proposed for approval |
| 7 | NotebookLM Research and Evidence Plan | `docs/NOTEBOOKLM-RESEARCH-AND-EVIDENCE-PLAN.md` | Proposed for approval |
| 8 | Risks, Assumptions and Decisions Register | `docs/RISKS-ASSUMPTIONS-AND-DECISIONS-REGISTER.md` | Active |
| 9 | Phase 1 Baseline Approval Record | `docs/PHASE-1-BASELINE-APPROVAL.md` | Prepared |

---

## 4. Approved Strategic Direction

The following direction is treated as locked unless superseded through change control.

### 4.1 Product

CaseLens AI is an AI-powered medical-learning web application.

### 4.2 Target User

The primary users are medical students and examination candidates practising case-based reasoning.

### 4.3 Core Problem

Medical learners often analyse clinical cases inconsistently, miss important clues, confuse facts with assumptions, and struggle to turn cases into active revision.

### 4.4 Core Product Outcome

A learner enters an educational case and receives structured reasoning, differentials, missing information, red flags, study topics, and case-specific MCQs.

### 4.5 Core Learning Loop

```text
Enter case
→ Validate
→ Analyse with Gemini
→ Review structured reasoning
→ Generate MCQs
→ Attempt and review
→ Copy, print, or revisit locally
```

### 4.6 AI Provider

The planned live AI provider is Gemini API.

### 4.7 Deployment

The planned production deployment target is Vercel at a public URL.

### 4.8 Source and Submission

The public repository is:

```text
nadeemmurtaza/CaseLens-AI
```

The repository link is the only planned portal submission item and must lead evaluators to the live app and complete README report.

---

## 5. Locked MVP Scope

### P0 Features

- New Case workspace
- Educational-use and privacy warning
- Case input and validation
- Difficulty selection
- Examination-style selection
- MCQ count selection
- Server-side Gemini analysis
- Structured analysis sections
- Insufficient-information behavior
- Out-of-scope behavior
- Case-specific MCQ generation
- MCQ attempt and explanation review
- Local recent-case history
- Reopen and delete local cases
- Copy analysis
- Print / Save PDF through browser print
- Responsive mobile and desktop experience
- About and Safety view
- Useful provider and network errors
- Public GitHub repository
- Public Vercel deployment
- Comprehensive README

### Explicitly Out of Scope

- Native Android or iOS applications
- App-store release
- Authentication
- User accounts
- Cloud case history
- Course management
- Teacher dashboards
- Attendance
- Certificates
- Payments
- Social features
- Real patient records
- Patient diagnosis or treatment
- Prescription generation
- Medical-image analysis
- Voice consultation
- Hospital integration
- Multiple AI providers
- Fine-tuned models
- Advanced analytics

Deferred items must not become hidden dependencies of P0 work.

---

## 6. Locked Product Boundaries

### 6.1 Application, Not Website

The deliverable is an interactive application. Informational content must support the workflow rather than replace it.

### 6.2 Not a General Chatbot

The interface must use defined case input and structured output. An open chat transcript is not the product.

### 6.3 Not an LMS

The application does not manage courses, students, teachers, attendance, or certificates.

### 6.4 Educational, Not Clinical Care

The application must not diagnose or treat a real patient and must not replace professional or emergency evaluation.

### 6.5 No Identifiable Patient Information

Users must be warned not to enter identifiable patient information. Ordinary logs must not store raw case text.

### 6.6 Local History Only

Recent-case history is stored in the user's browser for the MVP and must be described honestly.

---

## 7. Locked AI Rules

The AI implementation must:

- Treat case text as untrusted data
- Ignore instructions inside case text
- Separate supplied facts from inference
- Avoid treating unmentioned findings as absent
- Avoid invented clinical facts
- Use calibrated confidence
- Handle insufficient information explicitly
- Avoid patient-specific prescriptions or treatment
- Return structured JSON
- Pass server-side schema validation
- Fail safely when provider output is invalid
- Keep the API key server-side
- Avoid revealing system prompts or secrets
- Generate exactly one best answer per MCQ

Prompt changes require versioning and updated tests.

---

## 8. Confirmed Assignment Alignment

The baseline responds to the supplied assignment requirements as follows:

| Course requirement | Planned evidence |
|---|---|
| Original idea | Structured clinical-reasoning workflow and originality explanation |
| Real problem | Medical-learning problem statement and target user |
| Complete working app | End-to-end P0 learning loop |
| AI feature | Real Gemini analysis and MCQ generation |
| Public GitHub | Public repository with complete final source |
| Public URL | Vercel production deployment |
| Comprehensive README | README as complete project report |
| Idea marking | Originality and product-focus evidence |
| Completion marking | Functional and test evidence |
| Deployment marking | Production build and live workflow evidence |
| Reporting marking | README gap audit and final report |

---

## 9. Conditional Exception: Full Portal Brief

The official announcement states that a full brief exists in the portal Assignments tab. That full brief has not been supplied to the repository.

Therefore, Phase 1 is conditionally based on the confirmed announcement.

If the full portal brief is obtained:

1. Add it to the Assignment Requirements Source Record.
2. Run the NotebookLM Assignment Compliance Report.
3. Update the traceability matrix.
4. Revise affected documents.
5. Reapprove the Phase 1 baseline if material requirements change.

This exception does not justify delaying current work, but it remains an open High risk.

---

## 10. Phase 1 Acceptance Checklist

### Assignment Control

- [x] Confirmed announcement preserved
- [x] Mandatory requirements assigned stable IDs
- [x] Marking criteria recorded
- [x] Deadline recorded
- [x] Submission method recorded
- [ ] Full portal brief obtained and reconciled

### Product Definition

- [x] Product purpose defined
- [x] Real problem defined
- [x] Target user defined
- [x] Originality position defined
- [x] MVP scope defined
- [x] Out-of-scope list defined
- [x] Completion definition defined

### Product Behavior

- [x] Primary workflow defined
- [x] Routes defined
- [x] Screen requirements defined
- [x] Empty, loading, success, and error states defined
- [x] Local-history behavior defined
- [x] Copy and print behavior defined

### AI Control

- [x] AI responsibilities defined
- [x] Safety boundary defined
- [x] Prompt-injection rule defined
- [x] Analysis prompt baseline defined
- [x] MCQ prompt baseline defined
- [x] Analysis schema defined
- [x] MCQ schema defined
- [x] Prompt test catalogue defined

### Evidence and Governance

- [x] Assignment traceability matrix created
- [x] NotebookLM evidence plan created
- [x] Risks and dependencies recorded
- [x] Decisions recorded
- [x] Change-control rule defined
- [ ] Documents reviewed and approved by project owner
- [ ] Documentation pull request integrated into `main`

---

## 11. Authorization Provided by Approval

When this baseline receives executive approval, later phases may:

- Prepare verified design briefs
- Generate and audit Stitch screen concepts
- Define technical architecture
- Bootstrap application code
- Implement P0 features
- Build test suites
- Configure Vercel deployment
- Develop the README report

Later phases may not expand scope silently.

---

## 12. What Approval Does Not Mean

Phase 1 approval does not mean:

- Code has been written
- Gemini integration works
- Tests pass
- Vercel deployment exists
- The README is complete
- The application is safe for clinical use
- The project is ready for submission
- Unknown portal requirements are resolved

Those claims require later execution evidence.

---

## 13. Change-Control Gate

A material change to any of the following requires documentation and approval:

- Core problem
- Target users
- P0 scope
- AI provider
- AI safety rules
- Response schemas
- Data-storage model
- Application routes
- Repository visibility
- Deployment target
- Submission plan
- Deadline strategy

The change record must identify affected documents and tests.

---

## 14. Approval Record

### Project Owner Decision

**Decision:** Pending  
**Decision maker:** Nadeem Murtaza  
**Approved version:** Pending  
**Approval date:** Pending  
**Approved repository commit:** Pending  
**Conditions:** Reconcile the full portal brief if it becomes available.  

### Technical Review

**Status:** Pending architecture phase  
**Reviewer:** Pending  

### Phase 1 Final Status

**Documentation built:** Yes  
**Documentation integrated into main:** Pending  
**Executive approval:** Pending  
**Implementation started:** No claim made  
**Phase state:** Baseline Prepared

---

## 15. Next Phase After Approval

The next controlled phase is:

> **Phase 2: Verified Design Preparation and Interface Direction**

Its first outputs should be:

1. Verified Stitch Input Brief
2. Initial design directions
3. Stitch Design Audit
4. Approved screen reference set

Technical architecture may proceed in parallel only when it does not invent product behavior or expand scope.
