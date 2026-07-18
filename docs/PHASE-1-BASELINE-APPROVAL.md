# CaseLens AI

## Phase 1 Baseline Approval Record

### Document Control

**Project:** CaseLens AI  
**Document:** Phase 1 Baseline Approval Record  
**Version:** 1.1  
**Status:** Approved with Controlled Condition  
**Approval Date:** 18 July 2026  
**Submission Deadline:** Monday, 27 July 2026, 11:59 PM PKT  
**Repository:** `nadeemmurtaza/CaseLens-AI`  
**Pull Request:** `#1 — Build complete Phase 1 documentation baseline`

---

## 1. Approval Decision

The CaseLens AI Phase 1 documentation baseline is approved for integration into `main` and for use as the controlled foundation of later project phases.

This approval confirms that the project purpose, assignment interpretation, target users, MVP boundary, product behavior, user journeys, AI responsibilities, safeguards, evidence strategy, risks, assumptions, and change-control rules are sufficiently defined to proceed.

Approval does not claim that application code, Gemini integration, tests, deployment, screenshots, or the final README already exist.

---

## 2. Approved Baseline Documents

| # | Document | Repository path | Approval status |
|---|---|---|---|
| 1 | Assignment Requirements Source Record | `docs/ASSIGNMENT-REQUIREMENTS-SOURCE-RECORD.md` | Approved with source condition |
| 2 | Project Charter | `docs/PROJECT-CHARTER.md` | Approved |
| 3 | Product Requirements Document | `docs/PRODUCT-REQUIREMENTS.md` | Approved |
| 4 | Assignment Traceability Matrix | `docs/ASSIGNMENT-TRACEABILITY-MATRIX.md` | Approved |
| 5 | User Flows and Information Architecture | `docs/USER-FLOWS-AND-INFORMATION-ARCHITECTURE.md` | Approved |
| 6 | AI Feature and Prompt Specification | `docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md` | Approved |
| 7 | NotebookLM Research and Evidence Plan | `docs/NOTEBOOKLM-RESEARCH-AND-EVIDENCE-PLAN.md` | Approved |
| 8 | Risks, Assumptions and Decisions Register | `docs/RISKS-ASSUMPTIONS-AND-DECISIONS-REGISTER.md` | Approved as active register |
| 9 | Phase 1 Baseline Approval Record | `docs/PHASE-1-BASELINE-APPROVAL.md` | Approved |

---

## 3. Approved Product Direction

CaseLens AI is an AI-powered medical-learning web application for practising structured clinical reasoning.

The primary users are medical students and examination candidates who need to analyse educational cases, distinguish supplied facts from inference, understand diagnostic reasoning, compare differentials, identify missing information, recognise red flags, and practise case-specific MCQs.

The approved core learning loop is:

```text
Enter educational case
→ Validate input
→ Analyse with Gemini
→ Review structured reasoning
→ Generate case-specific MCQs
→ Attempt and review explanations
→ Copy, print, or revisit locally
```

The application is not approved as:

- A general-purpose chatbot
- A learning-management system
- A real-patient diagnostic system
- A treatment or prescription tool
- A native Android or iOS application

---

## 4. Approved P0 Scope

The approved MVP includes:

- New Case workspace
- Educational-use and privacy warning
- Clinical case input and validation
- Difficulty selection
- Examination-style selection
- MCQ quantity selection
- Server-side Gemini analysis
- Structured case analysis
- Insufficient-information handling
- Non-medical and unsafe-input handling
- Case-specific MCQ generation
- MCQ attempt, scoring, and explanation review
- Local recent-case history
- Reopen, delete, and clear-history behavior
- Copy analysis and MCQs
- Print or Save PDF through browser print
- Responsive mobile and desktop experience
- About and Safety view
- Useful network, provider, timeout, and validation errors
- Public GitHub repository
- Public Vercel deployment
- Comprehensive README project report

The following remain outside the MVP:

- Authentication and user accounts
- Cloud case history
- Courses, attendance, certificates, or instructor dashboards
- Payments or subscriptions
- Social and collaboration features
- Real patient records
- Patient diagnosis or treatment
- Prescription generation
- Medical-image analysis
- Hospital integration
- Multiple AI providers
- Fine-tuned models
- Advanced analytics

---

## 5. Approved AI Boundaries

The implementation must:

- Treat submitted case text as untrusted data
- Ignore instructions embedded inside case text
- Separate supplied facts from inference
- Never treat an unmentioned finding as absent
- Avoid inventing history, examination, laboratory, or imaging facts
- Use calibrated confidence
- Handle insufficient information explicitly
- Avoid patient-specific prescriptions and treatment instructions
- Return structured JSON
- Validate provider output server-side
- Fail safely when provider output is invalid
- Keep Gemini credentials server-side
- Avoid exposing prompts, secrets, or internal configuration
- Generate exactly one best answer for each MCQ

Material prompt changes require versioning and test updates.

---

## 6. Controlled Condition

The official course announcement states that a fuller assignment brief exists in the student portal. That full portal brief has not yet been supplied to the repository.

Phase 1 is therefore approved with this controlled condition:

> When the full portal brief becomes available, it must be compared against the Assignment Requirements Source Record and Assignment Traceability Matrix before final submission.

Required reconciliation steps:

1. Preserve the full brief or an accurate transcription in the source record.
2. Compare it with the current requirement IDs.
3. Add any missing requirements to the traceability matrix.
4. Update affected product, design, implementation, testing, deployment, and README requirements.
5. Reapprove the baseline only when the new brief materially changes the approved product.

This condition does not block Phase 2 because the confirmed announcement already establishes the central deliverables, marking categories, public repository requirement, live deployment requirement, AI requirement, README requirement, and deadline.

---

## 7. Acceptance Checklist

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
- [x] Target users defined
- [x] Originality position defined
- [x] MVP scope defined
- [x] Out-of-scope boundary defined
- [x] Completion definition defined

### Product Behavior

- [x] Primary workflow defined
- [x] Routes and information architecture defined
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
- [x] Risks, assumptions, and dependencies recorded
- [x] Decisions recorded
- [x] Change-control rule defined
- [x] Documents reviewed and approved by project owner
- [x] Documentation pull request authorized for integration into `main`

---

## 8. What This Approval Authorizes

Later phases may now:

- Prepare the verified design brief
- Generate and review interface directions
- Define technical architecture
- Bootstrap the application
- Implement P0 features
- Build automated and manual tests
- Configure Vercel deployment
- Build the comprehensive README
- Collect screenshots and submission evidence

Later phases may not silently expand scope or weaken the approved medical-safety boundaries.

---

## 9. What This Approval Does Not Prove

This approval does not prove that:

- Application code has been written
- Gemini works in development or production
- Tests pass
- Vercel is configured
- The live URL works
- The README is complete
- The project is ready for submission
- The application is safe for real clinical use
- The unavailable portal brief contains no additional requirement

Those claims require evidence from later phases.

---

## 10. Change-Control Gate

A material change requires a recorded decision and impact review when it affects:

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

The change record must identify all affected documents, implementation components, and tests.

---

## 11. Approval Record

**Decision:** Approved with Controlled Condition  
**Decision maker:** Nadeem Murtaza  
**Approved version:** Phase 1 baseline, version 1.1  
**Approval date:** 18 July 2026  
**Approval action:** Authorization to merge PR #1 into `main`  
**Condition:** Reconcile the full portal brief when it becomes available.  

### Phase 1 Status

**Documentation built:** Yes  
**Project-owner approval:** Yes  
**Authorized for integration:** Yes  
**Implementation completion claimed:** No  
**Submission readiness claimed:** No  
**Phase state after successful merge:** Complete with one controlled source-reconciliation condition

---

## 12. Next Phase

After successful integration into `main`, the next controlled phase is:

> **Phase 2: Verified Design Preparation and Interface Direction**

Its first outputs are:

1. Verified Stitch Input Brief
2. Initial interface directions
3. Stitch Design Audit
4. Approved screen reference set

Technical architecture may proceed in parallel only where it implements approved product behavior and does not expand scope.