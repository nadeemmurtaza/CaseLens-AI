# CaseLens AI

> An AI-powered medical-learning application for practising structured clinical reasoning through educational cases and case-specific MCQs.

## Project Status

| Area | Current status |
|---|---|
| Assignment requirements | Defined |
| Product concept | Defined |
| Phase 1 documentation | Integrated into `main` |
| Interface design | In progress |
| Application implementation | Not started |
| Gemini integration | Not started |
| Automated tests | Not started |
| Public deployment | Not available yet |
| Submission readiness | Not ready |

**Course:** ACT AI Final Course Project  
**Submission deadline:** Monday, 27 July 2026 at 11:59 PM PKT  
**Submission format:** Public GitHub repository link  
**Planned deployment:** Vercel  
**Planned AI provider:** Gemini API

> This README reflects the current repository state. It does not claim that the application, AI workflow, tests, or deployment already exist.

---

## Table of Contents

1. [Overview](#overview)
2. [Problem](#problem)
3. [Proposed Solution](#proposed-solution)
4. [Originality](#originality)
5. [Target Users](#target-users)
6. [Core User Journey](#core-user-journey)
7. [Planned MVP Features](#planned-mvp-features)
8. [AI-Powered Feature](#ai-powered-feature)
9. [Structured Analysis Output](#structured-analysis-output)
10. [Case-Specific MCQs](#case-specific-mcqs)
11. [Recent Cases](#recent-cases)
12. [Safety and Privacy](#safety-and-privacy)
13. [Planned Technology Stack](#planned-technology-stack)
14. [Planned Architecture](#planned-architecture)
15. [Design Direction](#design-direction)
16. [Error Handling](#error-handling)
17. [Testing Strategy](#testing-strategy)
18. [Deployment Plan](#deployment-plan)
19. [Assignment Alignment](#assignment-alignment)
20. [Project Documentation](#project-documentation)
21. [Local Development](#local-development)
22. [Known Limitations](#known-limitations)
23. [Future Improvements](#future-improvements)
24. [Author](#author)

---

## Overview

CaseLens AI is a focused educational web application that helps medical learners practise structured clinical reasoning.

A learner enters an educational clinical case. The application will validate the input, send it securely to Gemini, display a structured analysis, generate case-specific multiple-choice questions, explain the answers, and store a limited recent-case history locally on the learner's device.

CaseLens AI is not intended to be a general chatbot, hospital information system, patient-record platform, or clinical decision-support tool.

The product is built around one complete learning loop:

```text
Enter an educational case
→ Validate the input
→ Generate a structured analysis
→ Review findings and reasoning
→ Generate case-specific MCQs
→ Attempt the questions
→ Review answers and explanations
→ Copy, print, or revisit the case locally
```

---

## Problem

Medical learners often know isolated facts but struggle to apply them consistently to clinical cases.

Common difficulties include:

- Jumping directly to a diagnosis
- Missing important clinical clues
- Treating unmentioned information as absent
- Confusing supplied facts with assumptions
- Producing poorly prioritised differential diagnoses
- Failing to identify missing information
- Memorising answers without understanding the reasoning
- Using general AI chatbots that return unstructured or overly confident responses
- Struggling to convert one case into useful active-recall material

These problems make case-based learning less systematic and less useful for examination preparation.

---

## Proposed Solution

CaseLens AI will transform an unstructured educational case into a controlled learning experience.

The application will:

1. Validate whether the input is suitable for educational analysis.
2. Separate supplied facts from interpretation.
3. Identify important positive and explicitly supplied negative findings.
4. Present a calibrated most-likely diagnosis when sufficient information exists.
5. Explain the reasoning connecting the findings to the interpretation.
6. Compare reasonable differential diagnoses.
7. Identify missing history, examination findings, or investigations.
8. Highlight red flags in educational language.
9. Recommend relevant study topics.
10. Generate case-specific MCQs and explanations.

The objective is not merely to provide an answer. The objective is to help the learner understand how the case should be approached.

---

## Originality

CaseLens AI is not a renamed text box connected to an AI model.

Its originality comes from combining the following into one structured workflow:

- Clinical-case input validation
- Separation of supplied facts and inference
- Positive and negative finding analysis
- Calibrated diagnostic reasoning
- Differential diagnosis comparison
- Missing-information detection
- Red-flag identification
- Case-specific study recommendations
- Case-specific MCQ generation
- Answer explanations and learning objectives
- Local revision history
- Copy and print support

Gemini is the reasoning engine inside the workflow. The workflow itself is the product.

---

## Target Users

CaseLens AI is intended for medical learners with basic clinical knowledge, including:

- MBBS students
- NRE candidates
- USMLE candidates
- PLAB candidates
- MRCP candidates
- Other learners practising case-based reasoning

The application is not designed for real-patient diagnosis or treatment.

---

## Core User Journey

### 1. Start a New Case

The learner enters or pastes an educational clinical case.

### 2. Configure the Analysis

The learner selects:

**Difficulty**

- Basic
- Intermediate
- Advanced

**Examination style**

- General
- NRE
- USMLE
- PLAB
- MRCP

**MCQ quantity**

- 3
- 5
- 10

### 3. Validate the Input

The application checks for:

- Empty input
- Input that is too short
- Input exceeding the 12,000-character limit
- Clearly non-medical input
- Unsafe requests
- Possible identifiable patient information

### 4. Analyse the Case

The case is processed through a server-side Gemini request.

### 5. Review the Structured Analysis

The learner reviews supplied facts, findings, reasoning, differentials, missing information, red flags, and study topics.

### 6. Practise MCQs

The learner answers case-specific questions and receives explanations.

### 7. Revisit the Case

Successful analyses may be stored locally in a limited recent-case history.

---

## Planned MVP Features

### New Case

- Educational-use warning
- Patient-privacy warning
- Clinical-case text area
- Example-case action
- Reset form action
- Difficulty selection
- Examination-style selection
- MCQ quantity selection
- Input validation
- Analyse Case action

### Case Analysis

- Input assessment
- Case summary
- Supplied facts
- Important positive findings
- Important negative findings
- Most likely diagnosis
- Calibrated confidence
- Clinical reasoning
- Differential diagnoses
- Missing information
- Red flags
- Suggested study topics
- Educational disclaimer

### MCQ Practice

- 3, 5, or 10 generated questions
- Four options per question
- Exactly one correct answer
- Selected-answer state
- Correct and incorrect feedback
- Explanation
- Learning objective
- Progress indicator
- Final score
- Detailed results review

### Recent Cases

- Local-device storage
- Maximum of approximately 10 recent cases
- Reopen analysis
- Delete one case
- Clear all cases
- Empty-history state

### Supporting Functions

- Copy complete analysis
- Copy individual sections
- Copy MCQ results
- Print or save analysis as PDF through browser printing
- Responsive desktop and mobile layouts
- About & Safety page
- Useful failure messages

---

## AI-Powered Feature

The planned AI feature uses Gemini through server-side application routes.

Gemini will be responsible for:

- Assessing whether the input is suitable for analysis
- Producing structured clinical reasoning
- Identifying relevant findings
- Suggesting reasonable differential diagnoses
- Identifying missing information
- Highlighting educational red flags
- Recommending study topics
- Generating case-specific MCQs

The model response will not be rendered directly as unvalidated free text. The server will require structured JSON and validate it before returning it to the client.

### Planned Input Assessment States

- `VALID`
- `INSUFFICIENT`
- `NON_MEDICAL`
- `UNSAFE`

### Planned Confidence Levels

- Low
- Moderate
- High

Confidence will describe the educational interpretation based on supplied information. It will not represent clinical confirmation.

---

## Structured Analysis Output

The planned analysis contract contains:

```text
inputAssessment
caseSummary
suppliedFacts
positiveFindings
negativeFindings
mostLikelyDiagnosis
clinicalReasoning
differentials
missingInformation
redFlags
studyTopics
disclaimer
```

### Important Data Rule

CaseLens AI must never treat silence as a negative finding.

```text
Explicitly denied or documented absent
→ Important Negative Findings

Not mentioned
→ Missing Information or omitted
```

The system must not invent symptoms, examination findings, investigations, history, or timelines.

---

## Case-Specific MCQs

Generated MCQs must be traceable to the analysed case or its directly relevant learning topics.

Each question will contain:

- Question identifier
- Question stem
- Four options labelled A–D
- One correct answer
- Explanation
- Learning objective
- Difficulty
- Source section

Questions may test:

- Recognition of important findings
- Interpretation of the case
- Differential diagnosis
- Relevant pathophysiology
- Missing-information priorities
- Case-related examination concepts

The application must not behave as an unrelated generic question bank.

---

## Recent Cases

Recent cases will be stored in browser `localStorage` for the MVP.

Planned storage key:

```text
caselens_recent_cases_v1
```

Storage rules:

- Stored only on the current device and browser
- Maximum of approximately 10 successful analyses
- Newest cases displayed first
- Failed requests are not saved
- Individual cases can be removed
- All local history can be cleared
- No cloud synchronisation
- No user account required

Users will be told clearly that local browser storage is not a secure patient-record system.

---

## Safety and Privacy

CaseLens AI is for educational use only.

It must not:

- Diagnose a real patient
- Prescribe medication
- Recommend individual treatment
- Replace professional clinical judgment
- Replace emergency evaluation
- Provide medical clearance
- Store real patient records
- Claim certainty without sufficient evidence
- Encourage users to ignore qualified clinicians

Users must not enter identifiable patient information such as:

- Names
- CNIC or passport numbers
- Phone numbers
- Email addresses
- Addresses
- Hospital record numbers
- Any other direct identifier

### Planned Privacy Model

- Gemini requests processed through server-side routes
- API key kept on the server
- No account system in the MVP
- No cloud case-history database
- No ordinary logging of complete case text
- No intentional server retention after the request completes
- Local recent-case storage controlled by the user

AI output may be incomplete or incorrect and must be reviewed critically against trusted educational sources.

---

## Planned Technology Stack

| Layer | Planned technology |
|---|---|
| Web framework | Next.js with App Router |
| Language | TypeScript |
| Styling | Tailwind CSS |
| AI provider | Gemini API |
| Validation | Zod or equivalent schema validation |
| Local storage | Browser `localStorage` |
| Source control | GitHub |
| Deployment | Vercel |
| UI exploration | Google Stitch and Figma |
| Evidence review | NotebookLM |

The final dependency versions will be selected and verified during repository bootstrap.

---

## Planned Architecture

```text
Browser
  ↓
Next.js application
  ↓
Server-side API routes
  ↓
Input and configuration validation
  ↓
Gemini API
  ↓
Structured JSON validation
  ↓
Safe application response
  ↓
Rendered analysis or MCQ experience
```

### Planned Public Routes

```text
/
/history
/about
```

### Planned API Routes

```text
POST /api/analyze
POST /api/generate-mcqs
```

### Planned Source Areas

```text
app/
components/
lib/
types/
docs/
```

The final repository structure will be recorded after implementation begins.

---

## Design Direction

The approved visual direction is calm, focused, and educational.

Planned characteristics include:

- Deep medical green for primary actions
- White and soft-neutral backgrounds
- Restrained borders and shadows
- Clear information hierarchy
- Accessible typography
- Responsive desktop and mobile layouts
- Accordion-based mobile analysis
- Focused MCQ practice views
- Limited decorative imagery

The application must not resemble:

- A hospital information system
- A patient portal
- A general AI chatbot
- An institutional LMS
- A marketing-heavy SaaS landing page

Authentication, signup, logout, institutional access, subscriptions, and user profiles are outside the MVP.

---

## Error Handling

Planned application error codes include:

- `INPUT_TOO_SHORT`
- `INPUT_TOO_LONG`
- `INVALID_CONFIGURATION`
- `RATE_LIMITED`
- `AI_UNAVAILABLE`
- `AI_INVALID_RESPONSE`
- `REQUEST_TIMEOUT`
- `INTERNAL_ERROR`

User-facing failures must:

- Preserve the submitted case where practical
- Avoid exposing stack traces or provider details
- Avoid displaying false success
- Provide an appropriate retry or edit action
- Distinguish validation errors from provider failures

---

## Testing Strategy

Testing has not started because application implementation has not started.

The planned verification strategy includes:

### Unit Tests

- Validation rules
- Response-schema parsing
- Confidence handling
- Local-history utilities
- Score calculation
- Error mapping

### Integration Tests

- Analyze API route
- MCQ-generation API route
- Provider-response validation
- Safe failure behavior
- Local-history persistence

### End-to-End Tests

- Submit a valid case
- View a successful analysis
- Handle insufficient information
- Generate MCQs
- Submit correct and incorrect answers
- Review the final score
- Reopen a recent case
- Delete and clear local history
- Copy and print results

### Manual Verification

- Mobile layout
- Desktop layout
- Keyboard navigation
- Focus visibility
- Screen-reader labels
- Loading and failure states
- Vercel production workflow

No test result will be claimed until the relevant check passes against the latest implementation.

---

## Deployment Plan

The application is planned for deployment on Vercel.

A completed deployment must prove:

- Public access without authentication
- Successful production build
- Correct Gemini environment-variable configuration
- Working production analysis requests
- Working MCQ generation
- Responsive mobile behavior
- Useful production errors
- No exposed API key
- Current GitHub source matching the deployed application

### Live Demo

**Not available yet.**

The live URL will be added here only after production deployment is verified.

---

## Assignment Alignment

| Assignment requirement | CaseLens AI response | Current evidence |
|---|---|---|
| Original idea | Structured case reasoning plus case-specific MCQs | Product documentation |
| Real problem | Medical learners struggle to analyse cases systematically | Project Charter and PRD |
| Complete working app | End-to-end learning loop is defined | Planned, not implemented |
| AI-powered feature | Gemini analysis and MCQ generation | Specified, not implemented |
| Public GitHub repository | Repository is public | Available now |
| Public live deployment | Vercel deployment planned | Not available yet |
| Comprehensive README | README is being built as the project report | Present in this branch |
| Idea marking | Originality and problem evidence | Documented |
| Completion marking | Functional and test evidence | Pending implementation |
| Deployment marking | Production URL and verification | Pending |
| Reporting marking | README, screenshots, setup, architecture and evidence | In progress |

---

## Project Documentation

Phase 1 project-control documents are stored in [`docs/`](./docs).

- [Assignment Requirements Source Record](./docs/ASSIGNMENT-REQUIREMENTS-SOURCE-RECORD.md)
- [Project Charter](./docs/PROJECT-CHARTER.md)
- [Product Requirements Document](./docs/PRODUCT-REQUIREMENTS.md)
- [Assignment Traceability Matrix](./docs/ASSIGNMENT-TRACEABILITY-MATRIX.md)
- [User Flows and Information Architecture](./docs/USER-FLOWS-AND-INFORMATION-ARCHITECTURE.md)
- [AI Feature and Prompt Specification](./docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md)
- [NotebookLM Research and Evidence Plan](./docs/NOTEBOOKLM-RESEARCH-AND-EVIDENCE-PLAN.md)
- [Risks, Assumptions and Decisions Register](./docs/RISKS-ASSUMPTIONS-AND-DECISIONS-REGISTER.md)
- [Phase 1 Baseline Approval Record](./docs/PHASE-1-BASELINE-APPROVAL.md)

These documents define the intended product. They do not independently prove that the application has been implemented.

---

## Local Development

Application setup instructions are not available yet because the source application has not been bootstrapped.

After implementation begins, this section will include verified commands for:

- Installing dependencies
- Creating local environment variables
- Starting the development server
- Running formatting, linting, type-checking and tests
- Building the production application

Planned environment variable:

```text
GEMINI_API_KEY=
```

The real key must never be committed to GitHub or exposed to client-side code.

---

## Known Limitations

Current project limitations include:

- Application code has not yet been implemented
- No live Gemini workflow exists yet
- No production deployment exists yet
- No automated test evidence exists yet
- The full portal assignment brief has not been added to the repository
- Final design corrections are still being consolidated

Planned MVP limitations include:

- Educational use only
- Text-based cases only
- No authentication
- No cloud history
- No image or radiology analysis
- No treatment or prescription generation
- No official examination-body affiliation
- AI output may be incorrect or incomplete

---

## Future Improvements

Potential post-submission improvements may include:

- Optional user accounts
- Secure cross-device history
- Saved quiz progress
- Additional case templates
- Educator-created case collections
- Expanded accessibility testing
- More detailed performance analytics
- Carefully governed cloud storage

These are not part of the current MVP and must not delay the complete core workflow.

---

## Author

**Nadeem Murtaza**  
ACT AI Final Course Project

---

## Educational Disclaimer

CaseLens AI is intended only for medical education and examination practice. It does not provide medical advice, diagnose patients, recommend individual treatment, or replace qualified professional judgment. Do not submit identifiable patient information.