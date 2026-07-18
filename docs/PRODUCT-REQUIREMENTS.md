# CaseLens AI

## Product Requirements Document

### Document Control

**Project:** CaseLens AI  
**Document:** Product Requirements Document  
**Version:** 1.1  
**Status:** Approved Phase 1 Baseline  
**Approval Date:** 18 July 2026  
**Submission Deadline:** Monday, 27 July 2026, 11:59 PM PKT  
**Product Type:** AI-powered medical-learning web application  
**Primary AI Provider:** Gemini API  
**Deployment Target:** Vercel  
**Source Repository:** `nadeemmurtaza/CaseLens-AI`

---

## 1. Purpose

This document defines the approved behavior of CaseLens AI for the course-project MVP.

It converts the Project Charter into testable product requirements covering:

- User input and validation
- Structured Gemini analysis
- MCQ generation and practice
- Local revision history
- Copy and print behavior
- Safety and privacy controls
- Error states
- Responsive behavior
- Deployment and reporting evidence

The AI response contracts in this document and in `docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md` are identical and jointly authoritative. Any earlier conflicting schema wording is superseded by version 1.1.

---

## 2. Product Summary

CaseLens AI is an interactive medical-learning application.

A learner enters an educational clinical case, selects a difficulty and examination style, and receives a structured analysis that separates supplied facts from interpretation. The learner can then generate case-specific MCQs, attempt them, review explanations, copy or print learning material, and revisit recent cases stored locally in the browser.

The approved learning loop is:

```text
Enter case
→ Validate input
→ Analyse with Gemini
→ Review structured reasoning
→ Generate MCQs
→ Attempt and review questions
→ Copy, print, or revisit locally
```

---

## 3. Product Objectives

CaseLens AI must:

1. Solve a real medical-learning problem.
2. Demonstrate an original, focused AI workflow rather than a general chatbot.
3. Provide one complete end-to-end application journey.
4. Use a real Gemini API integration.
5. Remain educational and avoid presenting generated output as clinical care.
6. Work on mobile and desktop.
7. Be deployable publicly on Vercel.
8. Be documented through a comprehensive public GitHub README.

---

## 4. Target Users

Primary users:

- MBBS students
- NRE candidates
- USMLE candidates
- PLAB candidates
- MRCP candidates
- Medical learners practising case-based reasoning

The product is not intended for:

- Patients seeking diagnosis
- Emergency use
- Clinical decision-making
- Hospitals storing patient records
- Teachers managing courses or attendance

---

## 5. Scope Priorities

### 5.1 P0: Submission-Critical MVP

All P0 requirements must be implemented before the application may be called complete.

- New Case workspace
- Educational-use and privacy warning
- Case input and validation
- Difficulty selection
- Examination-style selection
- MCQ count selection
- Protected server-side Gemini analysis
- Structured analysis rendering
- Insufficient-information behavior
- Out-of-scope behavior
- Case-specific MCQ generation
- MCQ attempt, scoring, and explanation review
- Local recent-case history
- Reopen one stored case
- Delete one stored case
- Clear all stored cases with confirmation
- Copy individual analysis sections
- Copy complete analysis
- Browser print / Save as PDF
- Responsive mobile and desktop behavior
- About and Safety view
- Useful provider, network, validation, and storage errors
- Public GitHub repository
- Public Vercel deployment
- Comprehensive README project report

### 5.2 P1: Valuable but Deferrable

P1 work may proceed only after all P0 requirements are functioning.

- Review all MCQs on one summary screen
- Copy or print the complete MCQ set
- Optional theme preference
- Optional keyboard shortcuts beyond essential accessibility
- Optional example-case library

### 5.3 Explicitly Out of Scope

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
- Social or collaboration features
- Real patient records
- Medical-image analysis
- Patient-specific treatment or prescriptions
- Hospital or electronic-record integration
- Multiple AI providers
- Fine-tuned models
- Advanced analytics

---

## 6. Application Routes and Views

The approved information architecture is:

| Route | View | Purpose |
|---|---|---|
| `/` | New Case | Enter and configure an educational case |
| `/analysis` | Case Analysis | Review validated structured analysis |
| `/practice` | MCQ Practice | Attempt generated questions and review explanations |
| `/recent` | Recent Cases | Reopen, delete, or clear locally stored cases |
| `/about` | About and Safety | Explain purpose, limitations, privacy, and AI use |

Equivalent state-driven panels are acceptable if browser navigation remains understandable and refresh behavior is safe.

---

## 7. Core User Journeys

### 7.1 Analyse a Case

1. User opens New Case.
2. User reads the educational and privacy notice.
3. User enters or pastes a clinical case.
4. User selects difficulty, examination style, and MCQ count.
5. User selects **Analyse Case**.
6. Client validation runs.
7. A protected server route sends the validated request to Gemini.
8. The server validates the returned JSON.
9. The application renders the analysis.
10. A valid analysis is saved locally.

### 7.2 Generate and Attempt MCQs

1. User opens a completed analysis.
2. User selects **Generate MCQs**.
3. The server sends validated case context to Gemini.
4. The server validates the MCQ JSON.
5. Questions appear one at a time or in an equally clear practice format.
6. User selects an answer.
7. Application reveals correctness and explanation.
8. Progress and final score are displayed.
9. Generated MCQs may be added to the local case record.

### 7.3 Revisit a Case

1. User opens Recent Cases.
2. User selects a saved case.
3. Application restores the validated analysis and available MCQs.
4. User may delete one record or clear all records after confirmation.

---

## 8. Functional Requirements

### 8.1 New Case Input

#### FR-INPUT-01 — Case Text — P0

The user must be able to type, paste, edit, and clear a clinical case.

#### FR-INPUT-02 — Empty Input — P0

Empty or whitespace-only input must be rejected before an API request.

#### FR-INPUT-03 — Minimum Useful Input — P0

Clearly meaningless or excessively short input must not be treated as a successful clinical analysis.

#### FR-INPUT-04 — Non-Medical Input — P0

Clearly non-medical input must return an out-of-scope result or client validation message.

#### FR-INPUT-05 — Privacy Warning — P0

The interface must warn users not to enter names, CNIC numbers, contact details, record numbers, or other identifiable patient information.

#### FR-INPUT-06 — Configuration — P0

The user must be able to select:

- Difficulty: `basic`, `intermediate`, or `advanced`
- Examination style: `general`, `NRE`, `USMLE`, `PLAB`, or `MRCP`
- MCQ count: `3`, `5`, or `10`

The product must not claim official affiliation with examination bodies.

#### FR-INPUT-07 — Duplicate Submission — P0

The Analyse action must be disabled or safely ignored while the current request is processing.

---

### 8.2 Analysis Request

#### FR-ANALYSIS-01 — Server-Side Provider Call — P0

Gemini requests must originate from a server-side route. The API key must never be exposed to browser code.

#### FR-ANALYSIS-02 — Structured JSON — P0

The server must request and validate structured JSON. Arbitrary Markdown must not be parsed into product state.

#### FR-ANALYSIS-03 — Fact Discipline — P0

The model must separate explicitly supplied facts from inference and must not invent history, examination, laboratory, imaging, or demographic details.

#### FR-ANALYSIS-04 — Negative Findings — P0

Only explicitly denied or absent findings may be listed as negative findings. Unmentioned findings must not be treated as absent.

#### FR-ANALYSIS-05 — Uncertainty — P0

The response must use calibrated confidence and must not present a diagnosis as confirmed without definitive supplied evidence.

#### FR-ANALYSIS-06 — Insufficient Information — P0

When information is insufficient, the response must:

- Use `status: "insufficient_information"`
- Avoid an unsupported definitive diagnosis
- Preserve supplied facts
- Explain why certainty is limited
- Identify missing information
- Avoid invented details

#### FR-ANALYSIS-07 — Out of Scope — P0

Non-medical, meaningless, prompt-extraction, or primarily instructional input must use `status: "out_of_scope"` and must not generate differentials or MCQs.

#### FR-ANALYSIS-08 — Safe Rendering — P0

Model output must be rendered as text through controlled components. Raw model HTML must never be injected.

#### FR-ANALYSIS-09 — Retry — P0

A malformed provider response may receive one controlled schema-correction retry. Repeated uncontrolled retries are forbidden.

---

## 9. Canonical Analysis Response Contract

This is the approved v1.1 logical contract.

```json
{
  "schemaVersion": "1.0",
  "status": "complete",
  "privacyWarning": null,
  "caseSummary": "string",
  "suppliedFacts": ["string"],
  "positiveFindings": [
    {
      "finding": "string",
      "significance": "string"
    }
  ],
  "negativeFindings": [
    {
      "finding": "string",
      "significance": "string"
    }
  ],
  "mostLikelyDiagnosis": {
    "name": "string",
    "confidence": "low",
    "explanation": "string"
  },
  "clinicalReasoning": ["string"],
  "differentialDiagnoses": [
    {
      "name": "string",
      "supportingFindings": ["string"],
      "opposingOrMissingFindings": ["string"],
      "relativeLikelihood": "lower"
    }
  ],
  "missingInformation": [
    {
      "item": "string",
      "whyItMatters": "string"
    }
  ],
  "redFlags": [
    {
      "finding": "string",
      "significance": "string"
    }
  ],
  "studyTopics": [
    {
      "topic": "string",
      "reason": "string"
    }
  ],
  "educationalDisclaimer": "string"
}
```

### 9.1 Allowed Analysis Values

`status`:

- `complete`
- `insufficient_information`
- `out_of_scope`

`mostLikelyDiagnosis.confidence`:

- `low`
- `moderate`
- `high`

`differentialDiagnoses[].relativeLikelihood`:

- `lower`
- `similar`
- `higher`

### 9.2 Nullable Diagnosis

`mostLikelyDiagnosis` may be `null` for insufficient-information and out-of-scope responses.

### 9.3 Clinical Reasoning Type

`clinicalReasoning` is an array of concise, learner-facing explanation points. It must not contain private chain-of-thought.

### 9.4 Invalid Analysis Response

If validation fails, the application must:

- Avoid rendering the response as successful
- Preserve the user's input
- Avoid logging raw case text
- Show a useful retry message
- Permit one controlled retry where appropriate

---

## 10. Analysis Presentation

A valid result must present:

1. Case Summary
2. Supplied Facts
3. Important Positive Findings
4. Important Negative Findings
5. Most Likely Diagnosis
6. Clinical Reasoning
7. Differential Diagnoses
8. Missing Information
9. Red Flags
10. Recommended Study Topics
11. Educational Disclaimer

The user must be able to:

- Copy an individual section
- Copy the complete analysis
- Start a new case
- Print or save the analysis as PDF using the browser print flow
- Generate MCQs

---

## 11. MCQ Requirements

#### FR-MCQ-01 — Availability — P0

A valid completed analysis must provide a Generate MCQs action.

#### FR-MCQ-02 — Grounding — P0

MCQs must be grounded in the validated case and analysis context and must not depend on invented facts.

#### FR-MCQ-03 — Quantity — P0

The response must contain exactly the requested number of questions.

#### FR-MCQ-04 — Options — P0

Each question must have exactly four options labelled A, B, C, and D.

#### FR-MCQ-05 — One Best Answer — P0

Each question must have exactly one unambiguously best answer.

#### FR-MCQ-06 — Explanation — P0

Each question must include a correct-answer explanation and a learning objective.

#### FR-MCQ-07 — Practice — P0

The user must be able to select an answer, reveal correctness, read the explanation, and continue.

#### FR-MCQ-08 — Progress and Score — P0

The application must show current progress and a final score containing number correct, total questions, and percentage.

The score must not be presented as an official exam prediction.

---

## 12. Canonical MCQ Response Contract

This is the approved v1.1 logical contract.

```json
{
  "schemaVersion": "1.0",
  "mcqs": [
    {
      "id": "q1",
      "stem": "string",
      "options": [
        { "id": "A", "text": "string" },
        { "id": "B", "text": "string" },
        { "id": "C", "text": "string" },
        { "id": "D", "text": "string" }
      ],
      "correctOptionId": "A",
      "explanation": "string",
      "distractorExplanations": {
        "B": "string",
        "C": "string",
        "D": "string"
      },
      "learningObjective": "string",
      "difficulty": "basic"
    }
  ]
}
```

The top-level wrapper is `mcqs`. The earlier `questions` wrapper is superseded.

Validation must confirm:

- Requested question count matches returned count
- IDs are unique
- Options are exactly A, B, C, and D
- Option text is non-empty and non-duplicated within a question
- `correctOptionId` matches one option
- Explanation and learning objective are non-empty
- Difficulty uses an approved value
- No question relies on invented case facts

---

## 13. Recent Local Cases

All local-history requirements are P0.

#### FR-HISTORY-01 — Local Storage — P0

A valid completed analysis must be saved in browser `localStorage` when storage is available.

#### FR-HISTORY-02 — Stored Fields — P0

A record may include:

- Local identifier
- Created date and time
- Short generated title
- Original case text
- Selected configuration
- Validated analysis
- Generated MCQs where available

#### FR-HISTORY-03 — Maximum Records — P0

The application must retain no more than 20 recent cases. When the limit is exceeded, the oldest record may be removed.

#### FR-HISTORY-04 — Reopen — P0

The user must be able to reopen a stored case.

#### FR-HISTORY-05 — Delete One — P0

The user must be able to delete one stored case.

#### FR-HISTORY-06 — Clear All — P0

The user must be able to clear all recent cases after confirmation.

#### FR-HISTORY-07 — Honest Storage Description — P0

The interface must state that recent cases are stored locally and are not securely synchronised or backed up.

#### FR-HISTORY-08 — Storage Failure — P0

If `localStorage` is unavailable or full, the current analysis must remain usable and the application must show a non-blocking warning.

---

## 14. Error Requirements

The application must handle:

- Empty input
- Meaningless or non-medical input
- Duplicate submission
- Network failure
- Provider timeout
- Provider unavailable
- Invalid provider JSON
- Schema-validation failure
- Rate limiting
- Local-storage failure

Errors must:

- Use plain language
- Avoid exposing secrets or stack traces
- Preserve user input where possible
- Provide an appropriate retry or return action
- Never claim success when the operation failed

---

## 15. Privacy and Security Requirements

- Gemini API keys must remain server-side.
- `.env.local` and secrets must never enter the public repository.
- `.env.example` must contain placeholders only.
- Raw clinical case text must not be included in ordinary server logs.
- Case input must be treated as untrusted data.
- Prompt instructions inside case text must be ignored.
- Generated content must be safely rendered.
- The application must warn against entering identifiable patient information.
- The application must not intentionally retain case text server-side after request completion.

---

## 16. Non-Functional Requirements

### 16.1 Responsive Design

The complete P0 workflow must function on mobile, tablet, laptop, and desktop.

### 16.2 Accessibility

- Controls must be keyboard accessible.
- Inputs must have labels.
- Focus must remain visible.
- Loading and error states must be announced meaningfully.
- Text must maintain readable contrast.

### 16.3 Performance

- Initial UI must remain usable while AI calls are pending.
- Loading states must be explicit.
- Fake progress percentages must not be displayed.
- Requests must have reasonable timeouts.

### 16.4 Reliability

The application must not lose the user's current case merely because an API request fails.

---

## 17. API Surface

Recommended protected routes:

- `POST /api/analyse`
- `POST /api/mcqs`

Both routes must:

- Validate request bodies
- Enforce approved enumeration values
- Apply size limits
- Call Gemini server-side
- Validate response schemas
- Return safe application errors
- Avoid logging raw case text

---

## 18. Acceptance Criteria

Phase 1 implementation will be considered compliant only when tests demonstrate:

1. Valid case submission produces a validated structured analysis.
2. Empty input makes no provider request.
3. Non-medical input is handled safely.
4. Unmentioned findings are not converted into negative findings.
5. Insufficient information does not produce unsupported certainty.
6. Analysis JSON matches the canonical v1.1 contract.
7. MCQ JSON uses the `mcqs` wrapper.
8. Exactly the requested number of MCQs is generated.
9. Every MCQ has four options and one correct answer.
10. The learner can complete a question set and receive a score.
11. A completed analysis is stored locally.
12. Stored cases can be reopened, deleted individually, and cleared together.
13. Storage failure does not destroy the current result.
14. Copy and print actions work.
15. Mobile layout supports the complete P0 journey.
16. API keys are absent from client bundles and repository history.
17. Production deployment performs real Gemini requests.
18. README documents setup, features, safety, testing, and live deployment.

---

## 19. Course Grading Alignment

| Marking area | Product evidence |
|---|---|
| Idea | Original structured clinical-reasoning workflow |
| Completion | Entire P0 learning loop works end to end |
| Deployment | Public Vercel URL with functioning Gemini integration |
| Reporting | Comprehensive README with evidence and limitations |

---

## 20. Approval and Change Control

This PRD version is approved as the Phase 1 product baseline.

A material change to any of the following requires a recorded decision and corresponding test updates:

- P0 scope
- AI provider
- Analysis response schema
- MCQ response schema
- Storage model
- Application routes
- Safety boundary
- Deployment target
- Submission method

The missing full portal brief remains a documented conditional risk. If later obtained, it must be reconciled without silently invalidating this baseline.

---

## 21. Final Phase 1 Product Status

**Product requirements defined:** Yes  
**Schema conflicts resolved:** Yes  
**Local history priority resolved:** Yes, P0  
**Project-owner approval:** Approved  
**Phase 1 product baseline:** Approved
