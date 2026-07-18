# CaseLens AI

## Phase 1 Baseline Approval Record

### Document Control

**Project:** CaseLens AI  
**Document:** Phase 1 Baseline Approval Record  
**Version:** 1.1  
**Status:** Approved  
**Approval Date:** 18 July 2026  
**Decision Maker:** Nadeem Murtaza  
**Submission Deadline:** Monday, 27 July 2026, 11:59 PM PKT  
**Repository:** `nadeemmurtaza/CaseLens-AI`

---

## 1. Purpose

This record formally approves the CaseLens AI Phase 1 baseline.

Approval authorizes verified design preparation and technical planning against the documented scope. It does not claim that application code, tests, Gemini integration, Vercel deployment, or the final README are complete.

---

## 2. Approval Decision

**Decision:** Approved  
**Decision Maker:** Nadeem Murtaza  
**Decision Date:** 18 July 2026  
**Initial Phase 1 documentation merge:** `abeb27b7d1accbec17092782b2926285d00b8660`  
**Consistency-resolution change:** `agent/approve-phase-1-baseline`  
**Approval Condition:** Reconcile the full portal assignment brief if it becomes available and revise the baseline only where the official brief introduces a material requirement.

The project owner explicitly instructed that the identified conflicts be resolved and Phase 1 be marked approved.

---

## 3. Approved Baseline Document Set

| # | Document | Repository path | Approved status |
|---|---|---|---|
| 1 | Assignment Requirements Source Record | `docs/ASSIGNMENT-REQUIREMENTS-SOURCE-RECORD.md` | Approved source record with conditional portal-brief exception |
| 2 | Project Charter | `docs/PROJECT-CHARTER.md` | Approved |
| 3 | Product Requirements Document | `docs/PRODUCT-REQUIREMENTS.md` | Approved v1.1 |
| 4 | Assignment Traceability Matrix | `docs/ASSIGNMENT-TRACEABILITY-MATRIX.md` | Approved |
| 5 | User Flows and Information Architecture | `docs/USER-FLOWS-AND-INFORMATION-ARCHITECTURE.md` | Approved |
| 6 | AI Feature and Prompt Specification | `docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md` | Approved v1.1 |
| 7 | NotebookLM Research and Evidence Plan | `docs/NOTEBOOKLM-RESEARCH-AND-EVIDENCE-PLAN.md` | Approved |
| 8 | Risks, Assumptions and Decisions Register | `docs/RISKS-ASSUMPTIONS-AND-DECISIONS-REGISTER.md` | Approved as active register |
| 9 | Phase 1 Baseline Approval Record | `docs/PHASE-1-BASELINE-APPROVAL.md` | Approved v1.1 |

---

## 4. Approved Strategic Direction

### 4.1 Product

CaseLens AI is an AI-powered medical-learning web application, not a static website, general chatbot, LMS, or clinical-care system.

### 4.2 Target Users

Primary users are medical students and examination candidates practising case-based reasoning.

### 4.3 Core Problem

Medical learners often analyse cases inconsistently, miss important clues, confuse facts with assumptions, and struggle to convert cases into active revision.

### 4.4 Core Product Outcome

A learner enters an educational case and receives structured reasoning, differential diagnoses, missing information, red flags, study topics, and case-specific MCQs.

### 4.5 Core Learning Loop

```text
Enter case
→ Validate input
→ Analyse with Gemini
→ Review structured reasoning
→ Generate MCQs
→ Attempt and review questions
→ Copy, print, or revisit locally
```

### 4.6 Technology Direction

- Next.js
- TypeScript
- Tailwind CSS
- Gemini API through protected server routes
- Browser `localStorage`
- Public GitHub repository
- Vercel deployment
- Google Stitch for design exploration
- NotebookLM for private research and evidence review

---

## 5. Approved P0 Scope

The following features are mandatory for the MVP:

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
- MCQ attempt, scoring, and explanation review
- Local recent-case history
- Reopen one local case
- Delete one local case
- Clear all local cases after confirmation
- Copy individual analysis sections
- Copy complete analysis
- Browser print / Save as PDF
- Responsive mobile and desktop experience
- About and Safety view
- Useful provider, network, validation, and storage errors
- Public GitHub repository
- Public Vercel deployment
- Comprehensive README project report

---

## 6. Approved Out-of-Scope Boundary

The MVP excludes:

- Native Android or iOS applications
- App-store publication
- Authentication
- User accounts
- Payments or subscriptions
- Cloud-synchronised case history
- Course management
- Teacher dashboards
- Attendance
- Certificates
- Social features
- Real patient records
- Patient-specific diagnosis or treatment
- Prescription generation
- Medical-image analysis
- Voice consultation
- Hospital integration
- Multiple AI providers
- Fine-tuned models
- Advanced analytics

Deferred items must not become hidden dependencies of P0 work.

---

## 7. Resolved Baseline Conflicts

### 7.1 Analysis Response Schema

**Resolved:** Yes

The PRD and AI specification now use the same canonical contract.

Approved choices:

- Diagnosis field: `mostLikelyDiagnosis`
- Diagnosis explanation field: `explanation`
- Clinical reasoning type: array of concise learner-facing strings
- Differential field names: `name`, `supportingFindings`, `opposingOrMissingFindings`, and `relativeLikelihood`
- Missing-information objects: `item` and `whyItMatters`
- Red-flag objects: `finding` and `significance`
- Study-topic objects: `topic` and `reason`

### 7.2 MCQ Response Wrapper

**Resolved:** Yes

The approved top-level wrapper is:

```json
{
  "schemaVersion": "1.0",
  "mcqs": []
}
```

The earlier `questions` wrapper is superseded.

### 7.3 Local History Priority

**Resolved:** Yes

Local history, reopening, individual deletion, clear-all behavior, honest storage description, and storage-failure handling are all P0 requirements.

---

## 8. Approved AI Rules

The implementation must:

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
- Keep the Gemini key server-side
- Avoid revealing prompts, secrets, or private chain-of-thought
- Generate exactly one best answer per MCQ

Prompt or schema changes require versioning and updated tests.

---

## 9. Assignment Alignment

| Course requirement | Approved CaseLens AI response |
|---|---|
| Original idea | Focused structured clinical-reasoning workflow |
| Real problem | Inconsistent case analysis and weak active revision |
| Complete working app | Full P0 loop from case input through local revision |
| AI-powered feature | Real Gemini analysis and MCQ generation |
| Public GitHub | `nadeemmurtaza/CaseLens-AI` |
| Public deployment | Vercel production URL |
| Comprehensive README | README serves as final project report |
| Idea marking | Originality and problem evidence |
| Completion marking | Functional and test evidence |
| Deployment marking | Production build and live workflow evidence |
| Reporting marking | Complete README and screenshots |

---

## 10. Conditional Portal-Brief Exception

The supplied announcement states that a fuller brief exists in the portal Assignments tab. That full brief has not been supplied to the repository.

The project owner accepts this as a conditional risk and approves Phase 1 based on the confirmed announcement.

If the full brief is later obtained:

1. Add its confirmed requirements to the Assignment Requirements Source Record.
2. Run the NotebookLM Assignment Compliance review.
3. Update the traceability matrix.
4. Revise affected documents only where necessary.
5. Record any material scope change.

This exception does not block the approved transition to Phase 2.

---

## 11. Phase 1 Acceptance Checklist

### Assignment Control

- [x] Confirmed announcement preserved
- [x] Mandatory requirements assigned stable IDs
- [x] Marking criteria recorded
- [x] Deadline recorded
- [x] Submission method recorded
- [x] Missing full portal brief recorded and conditionally accepted

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
- [x] Routes and views defined
- [x] Empty, loading, success, and error states defined
- [x] Local-history behavior defined as P0
- [x] Copy and print behavior defined

### AI Control

- [x] AI responsibilities defined
- [x] Safety boundary defined
- [x] Prompt-injection rule defined
- [x] Analysis prompt baseline defined
- [x] MCQ prompt baseline defined
- [x] Analysis schema aligned across documents
- [x] MCQ schema aligned across documents
- [x] Prompt test catalogue defined

### Evidence and Governance

- [x] Assignment traceability matrix created
- [x] NotebookLM evidence plan created
- [x] Risks and dependencies recorded
- [x] Decisions recorded
- [x] Change-control rule defined
- [x] Initial documentation PR integrated into `main`
- [x] Project owner approved Phase 1

---

## 12. Authorization Provided by Approval

Phase 2 may now:

- Prepare a verified Google Stitch design brief
- Generate design directions
- Audit generated screens against approved flows
- Select an approved screen reference set
- Define technical architecture
- Bootstrap application code
- Implement P0 features
- Build tests
- Prepare deployment and README evidence

Later phases may not expand scope silently.

---

## 13. What Approval Does Not Mean

Phase 1 approval does not mean:

- Application code is complete
- Gemini integration works
- Tests pass
- Vercel deployment exists
- README is complete
- The application is safe for clinical use
- The project is ready for final submission

Those claims require later execution evidence.

---

## 14. Change-Control Gate

A material change to any of the following requires a documented decision and corresponding updates:

- Core problem
- Target users
- P0 scope
- AI provider
- AI safety rules
- Analysis or MCQ schemas
- Data-storage model
- Application routes
- Repository visibility
- Deployment target
- Submission method
- Deadline strategy

---

## 15. Final Approval Record

**Project Owner:** Nadeem Murtaza  
**Decision:** Approved  
**Approval Date:** 18 July 2026  
**Approved Phase:** Phase 1 — Project Definition and Requirements Control  
**Initial merged baseline:** `abeb27b7d1accbec17092782b2926285d00b8660`  
**Schema conflicts resolved:** Yes  
**Local-history priority resolved:** Yes, P0  
**Portal-brief exception:** Accepted conditionally  
**Phase 1 state:** Complete and Approved  
**Authorized next phase:** Phase 2 — Verified Design Preparation and Interface Direction
