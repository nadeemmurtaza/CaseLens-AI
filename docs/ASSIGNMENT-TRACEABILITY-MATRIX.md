# CaseLens AI

## Assignment Traceability Matrix

### Document Control

**Project:** CaseLens AI  
**Document:** Assignment Traceability Matrix  
**Version:** 1.0  
**Status:** Proposed for Approval  
**Date:** 18 July 2026  
**Source Documents:** Assignment Requirements Source Record, Project Charter, Product Requirements Document  

---

## 1. Purpose

This matrix proves that every confirmed course requirement and marking criterion is connected to:

- A CaseLens AI product capability
- A verification method
- A required evidence item
- A README reporting section
- A release decision

A feature without traceability should not be added merely because it appears impressive. A requirement without evidence should not be declared satisfied merely because everyone remembers seeing something similar.

---

## 2. Traceability Status Values

| Status | Meaning |
|---|---|
| Planned | Requirement is mapped but not implemented |
| Changed | Relevant source or documentation exists |
| Verified Locally | Required local checks passed after the latest change |
| Verified in Production | The exact deployed build passed the required workflow |
| Complete | Requirement, evidence, reporting, and deployment checks all pass |
| Blocked | External dependency prevents verification |

At Phase 1, all implementation requirements remain **Planned**.

---

## 3. Assignment Requirement Matrix

| Assignment ID | Requirement | CaseLens AI response | Product requirement references | Verification | Required evidence | README section | Phase 1 status |
|---|---|---|---|---|---|---|---|
| AR-01 | Original idea | Purpose-built clinical-reasoning workflow, not a generic chatbot or LMS | PRD originality, structured analysis, MCQ workflow | Product comparison review; evaluator comprehension check | Originality brief; screenshots; workflow diagram | Problem, originality, comparison | Planned |
| AR-02 | Solve a real problem | Addresses inconsistent case analysis and weak reasoning practice among medical learners | PRD problem statement and user outcomes | User can explain the problem and how the workflow addresses it | Project Charter; user-flow evidence | Problem statement, target users | Planned |
| AR-03 | Complete working app | One complete loop from case entry to analysis, MCQs, copy, print, and local revisit | P0 functional requirements | End-to-end production test | Test results; screen recording or screenshots; live URL | Features, usage, testing | Planned |
| AR-04 | AI-powered feature | Gemini analyses cases and generates validated educational MCQs | AI analysis and MCQ contracts | Real production request with valid and invalid cases | API evidence; output screenshots; test cases | AI feature, architecture, safety | Planned |
| AR-05 | Public GitHub repository | Complete source and documentation live in public repository | Repository requirements | Anonymous repository access check | Public repository URL; final commit SHA | Repository and project structure | Changed |
| AR-06 | Live public deployment | Next.js application deployed on Vercel | Deployment requirements | Anonymous production access; production AI workflow test | Vercel URL; deployment screenshot; production test record | Live demo, deployment | Planned |
| AR-07 | Comprehensive README | README serves as full project report | README requirements | README gap audit against all required sections | Final README; NotebookLM gap report | Entire README | Planned |
| AR-08 | Submit only repo link | Repository provides the live URL and all evidence | Repository-as-submission-hub constraint | Follow repository link as an evaluator and reach all evidence | Repository landing page; README links | Top section and live demo | Planned |
| AR-09 | Meet deadline | Scope and release plan prioritize P0 completion before 27 July 2026, 11:59 PM PKT | Deadline and priority rules | Submission timestamp and final repository state | Portal submission record; final commit | Project status | Planned |

---

## 4. Marking-Criterion Matrix

### 4.1 Idea

| Evidence question | Planned answer | Product evidence | Verification |
|---|---|---|---|
| Is the idea specific? | Yes. It targets clinical-reasoning practice for medical learners. | Charter and PRD | Reviewer reads problem and target-user sections |
| Is it more than a chatbot? | Yes. The application enforces defined input, structured output, safety, MCQs, and revision flow. | AI specification and user flows | Compare against generic chat behavior |
| Does it solve a real problem? | Yes. It structures case interpretation and converts cases into active revision. | Problem statement and user outcomes | User-comprehension review |
| Is AI appropriate? | Yes. Gemini performs language-based case interpretation and question generation inside controlled contracts. | AI feature specification | Prompt and output validation tests |
| Is scope focused? | Yes. LMS, patient care, accounts, cloud history, and image diagnosis are excluded. | Charter and risk register | Scope audit |

### 4.2 Completion

| Completion area | P0 behavior | Acceptance evidence |
|---|---|---|
| Case entry | User can enter, edit, clear, and submit an educational case | Functional and E2E test |
| Validation | Empty, short, meaningless, and non-medical input receive useful errors | Validation tests |
| AI analysis | Gemini returns a validated structured analysis | Integration and production test |
| Uncertainty | Insufficient cases do not receive fabricated certainty | Adversarial prompt tests |
| MCQ practice | User generates, answers, and reviews case-specific MCQs | Functional test and screenshots |
| Local history | Successful cases can be reopened and deleted locally | Browser test |
| Copy and print | Analysis and MCQs can be copied and printed cleanly | Manual browser test |
| Error behavior | Network, provider, timeout, and invalid-output failures are useful and non-destructive | Failure-injection tests |
| Responsive use | Primary workflow works on mobile and desktop | Viewport and device tests |
| No blocker | No known P0 defect remains | Final defect register |

### 4.3 Deployment

| Deployment area | Requirement | Evidence |
|---|---|---|
| Build | Production build completes against final commit | Vercel build record |
| Public access | App opens without login | Anonymous browser test |
| AI production flow | Gemini request succeeds through deployed server route | Production workflow record |
| Environment variables | Real key exists only in Vercel environment settings | Secret scan and deployment configuration review |
| Mobile production | Case entry, analysis, and MCQ flow work on mobile | Mobile screenshots and test result |
| Failure behavior | Public deployment shows useful provider/network errors | Production-safe failure test |
| Repository link | README links to the exact live deployment | Link verification |

### 4.4 Reporting

| README section | Source document | Evidence expected |
|---|---|---|
| Project overview | Project Charter | Concise product summary |
| Problem statement | Charter and PRD | Real problem and target user |
| Originality | Charter and traceability matrix | Difference from chatbot and LMS |
| Features | PRD | Implemented P0 feature list |
| Application workflow | User Flows document | Diagram and screen sequence |
| AI feature | AI specification | Gemini role, prompt rules, response validation |
| Technology stack | Technical architecture, later phase | Framework and services |
| Setup | Implementation repository | Reproducible local instructions |
| Environment variables | AI and deployment specifications | Placeholder-only `.env.example` |
| Testing | Testing plan and results, later phase | Commands, scenarios, outcomes |
| Deployment | Deployment plan and Vercel evidence, later phase | Public URL and process |
| Screenshots | Final application | Current production screens |
| Safety and privacy | AI specification and risk register | Educational boundary and no-PII rule |
| Limitations | Risk register and final audit | Honest unresolved limitations |
| Future work | Deferred requirements | Clearly separated from delivered scope |

---

## 5. Product Feature Traceability

| Feature ID | Feature | Assignment contribution | Acceptance focus | Evidence owner |
|---|---|---|---|---|
| F-01 | Case workspace | Completion, idea | Input is usable and focused | Application tests |
| F-02 | Input validation | Completion | Invalid cases fail clearly | Unit and E2E tests |
| F-03 | Gemini structured analysis | AI, completion, idea | Valid schema; facts and inference separated | API tests |
| F-04 | Insufficient-information behavior | Idea, completion | No invented certainty | Prompt-quality tests |
| F-05 | Differential diagnosis | Idea | Alternatives have supporting/opposing reasoning | Sample-output review |
| F-06 | Red flags and study topics | Idea | Educational and appropriately bounded | Medical-content review |
| F-07 | MCQ generation | AI, completion | Questions are case-related and answerable | MCQ validation tests |
| F-08 | MCQ practice state | Completion | Answer selection and review work | UI tests |
| F-09 | Local recent cases | Completion | Local-only persistence and deletion work | Browser-storage tests |
| F-10 | Copy and print | Completion | Clean, readable outputs | Manual browser tests |
| F-11 | Responsive application shell | Completion, deployment | Mobile and desktop workflow | Responsive tests |
| F-12 | About and safety view | Reporting, idea | Purpose, limits, and privacy are clear | Content review |

---

## 6. Evidence Register

| Evidence ID | Evidence | Created during | Required before final submission |
|---|---|---|---|
| EV-01 | Official assignment source record | Phase 1 | Yes |
| EV-02 | Approved Project Charter | Phase 1 | Yes |
| EV-03 | Product Requirements Document | Phase 1 | Yes |
| EV-04 | Assignment Traceability Matrix | Phase 1 | Yes |
| EV-05 | User Flows and Information Architecture | Phase 1 | Yes |
| EV-06 | AI Feature and Prompt Specification | Phase 1 | Yes |
| EV-07 | Risk and decision register | Phase 1 onward | Yes |
| EV-08 | Stitch design brief and selected screens | Design phase | Yes |
| EV-09 | Technical architecture | Architecture phase | Yes |
| EV-10 | Automated test output | Development and testing | Yes |
| EV-11 | Manual mobile and desktop test record | Testing | Yes |
| EV-12 | Gemini prompt-quality test report | Testing | Yes |
| EV-13 | Secret scan result | Security verification | Yes |
| EV-14 | Final production screenshots | Release | Yes |
| EV-15 | Public Vercel URL | Release | Yes |
| EV-16 | Final commit SHA | Release | Yes |
| EV-17 | Final README | Reporting | Yes |
| EV-18 | NotebookLM README gap report | Reporting | Yes |
| EV-19 | Final submission audit | Release | Yes |
| EV-20 | Portal submission record | Submission | Yes |

---

## 7. Requirement-to-Test Mapping

| Requirement area | Test categories |
|---|---|
| Case input | Empty, short, valid, long, non-medical, whitespace-only |
| AI analysis | Normal case, ambiguous case, insufficient case, malformed provider output |
| Safety | Identifiable information warning, patient-specific advice request, unjustified certainty |
| MCQs | Correct count, valid options, one correct answer, explanation, case relevance |
| Reliability | Timeout, network failure, provider error, repeated submission |
| Local history | Save, reopen, delete one, clear all, storage unavailable |
| Copy and print | Full copy, section copy, print layout, mobile print behavior |
| Responsive UI | 320px mobile through desktop, no horizontal overflow |
| Accessibility | Keyboard, focus, labels, errors, status announcements, contrast |
| Deployment | Production build, public route, server API, environment variables |
| Reporting | README section checklist and link validation |

---

## 8. Deferred Items

The following do not contribute enough to the confirmed marking criteria to justify MVP risk:

- Authentication
- Cloud history
- Native mobile applications
- Medical-image analysis
- Voice input
- Social sharing
- Teacher dashboards
- Course management
- Payments
- Multi-provider AI routing
- Fine-tuned models

They may appear only under future improvements and must not be represented as completed.

---

## 9. Traceability Review Gate

Before Phase 1 approval:

- Every confirmed assignment requirement must have a feature or reporting response.
- Every P0 feature must map to acceptance evidence.
- Every required evidence item must have a planned repository location.
- No deferred item may appear as an MVP dependency.
- Unknown portal requirements must remain visible.

---

## 10. Current Status

**Confirmed assignment requirements mapped:** Yes  
**Marking criteria mapped:** Yes  
**MVP features mapped:** Yes  
**Evidence register created:** Yes  
**Implementation evidence available:** No  
**Production evidence available:** No  
**Phase 1 status:** Changed; pending document review and baseline approval
