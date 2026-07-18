# CaseLens AI

## Product Requirements Document

### Document Control

**Project:** CaseLens AI  
**Document:** Product Requirements Document  
**Version:** 1.0  
**Status:** Proposed for Approval  
**Date:** 18 July 2026  
**Submission Deadline:** Monday, 27 July 2026, 11:59 PM PKT  
**Product Type:** AI-powered medical-learning web application  
**Primary AI Provider:** Gemini API  
**Deployment Target:** Vercel  
**Source Repository:** Public GitHub repository

---

## 1. Purpose

This document defines exactly what CaseLens AI must do, how users interact with it, what the AI must return, how failure states must behave, and what evidence is required before the application may be considered complete.

The Project Charter defines why CaseLens AI exists and what belongs inside the MVP. This Product Requirements Document converts that approved direction into implementation-ready product behavior.

---

## 2. Product Summary

CaseLens AI is an interactive medical-learning application that helps learners practise structured clinical reasoning.

The user enters an educational clinical case. The application validates the input, sends it to Gemini through a protected server-side route, receives structured analysis, displays facts and inference separately, and allows the learner to generate examination-style MCQs from the same case.

The complete learning loop is:

```text
Enter case
→ Validate input
→ Analyse with Gemini
→ Review structured reasoning
→ Generate MCQs
→ Attempt questions
→ Review explanations
→ Copy, print or revisit locally
```

The application is not a diagnostic service, treatment system, hospital platform, electronic medical record, general chatbot or learning-management system.

---

## 3. Product Goals

### PG-01: Structured Reasoning

Help learners follow a consistent clinical-reasoning process instead of jumping directly to a diagnosis.

### PG-02: Fact Discipline

Separate facts explicitly supplied in the case from AI inference, uncertainty and missing information.

### PG-03: Educational Value

Turn one submitted case into a reusable learning package containing reasoning, differential diagnoses, red flags, study topics and MCQs.

### PG-04: Safe AI Use

Prevent the application from presenting itself as a substitute for qualified medical judgment or patient-specific care.

### PG-05: Complete Submission

Deliver a functional, publicly deployed application with a public repository and comprehensive README before the course deadline.

---

## 4. Non-Goals

The MVP will not provide:

- Native Android or iOS applications
- User accounts or authentication
- Cloud case history
- Real patient record storage
- Patient diagnosis
- Treatment recommendations
- Prescription generation
- Medical-image analysis
- Laboratory or radiology interpretation from uploaded files
- Voice consultation
- Institution, teacher or student administration
- Courses, attendance, certificates or assignments
- Payment or subscription features
- Collaboration or social sharing
- Multiple AI-provider routing
- Fine-tuned medical models
- Advanced analytics dashboards

Any feature outside this list requires explicit scope change. It must not be added merely because implementation has become temporarily exciting.

---

## 5. Target Users

### 5.1 Primary User

A medical learner who:

- Has basic medical knowledge
- Wants to practise case-based reasoning
- May be preparing for NRE, USMLE, PLAB, MRCP or general medical examinations
- Uses mobile or desktop devices
- Needs explanations rather than only final answers
- Understands that the output is educational

### 5.2 Excluded Use

The application is not intended for:

- Patients seeking diagnosis or treatment
- Emergency medical decision-making
- Clinical documentation
- Real patient management
- Professional use without independent verification

---

## 6. Product Principles

### PP-01: Application Before Marketing

The opening view must lead quickly into the case-analysis workflow. It must not become a long promotional homepage.

### PP-02: Facts Before Conclusions

Supplied facts must appear before diagnostic interpretation.

### PP-03: Uncertainty Is Valid Output

The system must state when the information is insufficient. It must not manufacture certainty merely to fill a card.

### PP-04: Education Before Advice

The application may explain clinical concepts and red flags but must not provide individualized patient-management instructions.

### PP-05: One Complete Workflow

The MVP must prioritise one reliable end-to-end workflow over many partially implemented features.

### PP-06: Local Privacy by Default

Recent cases will remain in browser storage. No cloud case database will be introduced in the MVP.

---

## 7. Priority Levels

### P0: Submission-Critical

The application cannot be submitted without this requirement.

### P1: Important

The feature should be included unless it threatens P0 completion.

### P2: Deferred

The feature is explicitly outside the current release.

---

## 8. Primary User Journey

### Journey J-01: Analyse a Clinical Case

1. User opens CaseLens AI.
2. User reads the short purpose and safety notice.
3. User enters or pastes an educational clinical case.
4. User optionally selects difficulty, examination style and MCQ quantity.
5. User selects **Analyse Case**.
6. The application validates the input.
7. The application sends a server-side request to Gemini.
8. The application receives and validates structured output.
9. The application displays the case analysis.
10. The application stores the completed case locally when local history is enabled.
11. The user may copy, print, generate MCQs or start a new case.

### Journey J-02: Practise MCQs

1. User opens a completed analysis.
2. User selects **Generate MCQs**.
3. The application displays a loading state.
4. Gemini returns validated MCQs related to the case.
5. The user answers one question at a time.
6. The application reveals whether the selected answer is correct.
7. The application displays the explanation and learning objective.
8. The application shows progress and final score.
9. The user may review all MCQs, print them or return to the analysis.

### Journey J-03: Reopen a Recent Case

1. User opens Recent Cases.
2. The application reads local browser storage.
3. User selects a saved case.
4. The application displays the stored analysis and available MCQs.
5. User may delete the case or clear all local history.

---

## 9. Information Architecture

The MVP should provide these routes or equivalent application views:

```text
/
  Welcome and case entry

/analysis
  Current structured analysis

/practice
  MCQ practice and results

/history
  Recent locally stored cases

/about
  Educational purpose, privacy and safety
```

The final routing implementation may use Next.js routes, panels or modal transitions, but each view must remain directly understandable and testable.

---

## 10. Functional Requirements

# 10.1 Welcome and Case Entry

### FR-ENTRY-01 — Application Identity — P0

The opening view must display:

- CaseLens AI
- A concise explanation of the application
- An educational-use notice
- A warning not to enter identifiable patient information
- A visible case-input area
- A primary **Analyse Case** action

### FR-ENTRY-02 — Immediate Workflow Access — P0

A user must be able to begin entering a case without navigating through marketing sections or creating an account.

### FR-ENTRY-03 — Example Guidance — P1

The input view should provide a short example or placeholder demonstrating acceptable educational case structure.

The example must not contain identifiable patient data.

### FR-ENTRY-04 — About and Safety Access — P0

The user must be able to open the About and Safety information before submitting a case.

---

# 10.2 Clinical Case Input

### FR-INPUT-01 — Text Entry — P0

The application must provide a multiline text area supporting typed and pasted case content.

### FR-INPUT-02 — Character Count — P1

The interface should show the current character count and maximum allowed length.

### FR-INPUT-03 — Input Limits — P0

The initial limits are:

- Minimum meaningful length: 80 characters
- Maximum length: 12,000 characters

Input below the minimum may be accepted only when the system can still identify meaningful clinical content. Otherwise, the application must request more information.

### FR-INPUT-04 — Empty Input — P0

The application must reject empty or whitespace-only submission.

Error message:

> Enter an educational clinical case before requesting analysis.

### FR-INPUT-05 — Non-Medical Input — P0

The application must detect clearly non-medical input through validation and AI response rules.

It must display a useful message instead of producing fabricated medical analysis.

### FR-INPUT-06 — Identifiable Information Warning — P0

The interface must instruct the user not to enter:

- Names
- CNIC or passport numbers
- Contact details
- Addresses
- Hospital record numbers
- Any other information that identifies a real patient

### FR-INPUT-07 — Clear Input — P0

The user must be able to clear the input.

If the field contains text, clearing should require a lightweight confirmation or provide an immediate undo where practical.

### FR-INPUT-08 — Preserve Input on Failure — P0

The application must preserve the submitted case when validation, network or AI processing fails, unless the user explicitly clears it.

---

# 10.3 Analysis Configuration

### FR-CONFIG-01 — Difficulty — P1

The user may select:

- Basic
- Intermediate
- Advanced

Default: Intermediate.

### FR-CONFIG-02 — Examination Style — P1

The user may select:

- General Medical
- NRE
- USMLE
- PLAB
- MRCP

Default: General Medical.

The interface must state that CaseLens AI is not affiliated with or endorsed by the named examination bodies.

### FR-CONFIG-03 — MCQ Quantity — P1

The user may select:

- 3
- 5
- 10

Default: 5.

The quantity affects later MCQ generation and does not need to generate MCQs during the initial case-analysis request.

---

# 10.4 Submission and Loading

### FR-SUBMIT-01 — Analyse Case — P0

Selecting **Analyse Case** must begin validation and, when valid, submit the request through a server-side application route.

### FR-SUBMIT-02 — Duplicate Prevention — P0

While a request is active:

- The submit action must be disabled or guarded
- Repeated clicks must not send duplicate Gemini requests
- The user must receive visible processing feedback

### FR-SUBMIT-03 — Loading State — P0

The loading view must:

- Explain that the case is being analysed
- Avoid fake progress percentages
- Keep the submitted case available
- Remain accessible to screen readers
- Avoid blocking browser navigation indefinitely

### FR-SUBMIT-04 — Request Timeout — P0

The server-side request must use a controlled timeout.

Recommended initial timeout: 45 seconds.

When the request times out, the application must show a retry option and preserve the case input.

---

# 10.5 AI Case Analysis

### FR-ANALYSIS-01 — Structured Output — P0

A successful analysis must contain these sections:

1. Case Summary
2. Supplied Facts
3. Important Positive Findings
4. Important Negative Findings
5. Most Likely Diagnosis
6. Clinical Reasoning
7. Differential Diagnoses
8. Missing or Useful Information
9. Red Flags
10. Recommended Study Topics
11. Educational Disclaimer

### FR-ANALYSIS-02 — Case Summary — P0

The summary must restate the case concisely without adding new facts.

### FR-ANALYSIS-03 — Supplied Facts — P0

This section must contain only information explicitly supplied by the user.

### FR-ANALYSIS-04 — Positive Findings — P0

The response must identify findings that support one or more diagnostic possibilities.

Each item should explain why the finding matters.

### FR-ANALYSIS-05 — Negative Findings — P0

The response must identify relevant absent or denied findings only when they are actually stated or safely derived from explicit wording.

The model must not assume that an unmentioned symptom is absent.

### FR-ANALYSIS-06 — Most Likely Diagnosis — P0

When sufficient evidence exists, the response may identify a leading diagnosis.

It must use calibrated language and state confidence as one of:

- Low
- Moderate
- High

The confidence label is educational and must not be represented as a validated clinical probability.

### FR-ANALYSIS-07 — Insufficient Information — P0

When evidence is insufficient:

- The leading diagnosis may be null or expressed as uncertain
- The response must state that the case cannot be resolved confidently
- Missing information must be listed
- No fabricated clinical data may be introduced

### FR-ANALYSIS-08 — Clinical Reasoning — P0

The reasoning section must connect supplied findings to the leading interpretation in clear educational language.

It must not expose hidden model chain-of-thought. It should provide a concise, user-facing rationale.

### FR-ANALYSIS-09 — Differential Diagnoses — P0

The response should contain up to five reasonable alternatives.

Each differential should include:

- Diagnosis name
- Supporting findings
- Findings against or missing
- Relative likelihood: lower, similar or higher compared with other alternatives

### FR-ANALYSIS-10 — Missing Information — P0

The response must identify additional history, examination findings or investigations that would materially improve interpretation.

It must not imply that the learner should order tests for a real patient through the application.

### FR-ANALYSIS-11 — Red Flags — P0

The response must identify urgent or high-risk features present in the supplied case.

If no red flag is identifiable, the response should say:

> No specific red flag was identified from the supplied information.

This statement must not imply that the case is clinically safe.

### FR-ANALYSIS-12 — Study Topics — P0

The response must suggest three to eight relevant topics for revision.

### FR-ANALYSIS-13 — Disclaimer — P0

Every completed analysis must show a visible educational disclaimer.

Required meaning:

> This output is for medical education only. It is not a diagnosis, treatment plan or substitute for qualified clinical judgment.

### FR-ANALYSIS-14 — Section-Level Copy — P1

The user should be able to copy individual sections.

### FR-ANALYSIS-15 — Full Copy — P0

The user must be able to copy the complete analysis in a readable text format.

### FR-ANALYSIS-16 — New Case — P0

The user must be able to return to an empty case-entry state without deleting previously saved local cases.

---

# 10.6 AI Response Contract

### FR-SCHEMA-01 — Validated JSON — P0

The Gemini response must be requested and validated as structured JSON.

The application must not rely on parsing arbitrary Markdown prose into product state.

### FR-SCHEMA-02 — Analysis Shape — P0

The expected logical response shape is:

```json
{
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
    "name": "string or null",
    "confidence": "low | moderate | high",
    "explanation": "string"
  },
  "clinicalReasoning": "string",
  "differentialDiagnoses": [
    {
      "name": "string",
      "supportingFindings": ["string"],
      "opposingOrMissingFindings": ["string"],
      "relativeLikelihood": "lower | similar | higher"
    }
  ],
  "missingInformation": ["string"],
  "redFlags": ["string"],
  "studyTopics": ["string"],
  "educationalDisclaimer": "string"
}
```

### FR-SCHEMA-03 — Invalid Response — P0

If the response fails schema validation, the application must:

- Avoid displaying it as a successful analysis
- Record a safe technical error without storing full case text
- Provide a retry option
- Preserve the user’s input

### FR-SCHEMA-04 — Safe Rendering — P0

AI-generated content must be rendered as text or through safely controlled components.

Raw HTML from the model must not be injected into the page.

---

# 10.7 MCQ Generation

### FR-MCQ-01 — Generate MCQs — P0

A completed case analysis must provide a **Generate MCQs** action.

### FR-MCQ-02 — Case Grounding — P0

Generated MCQs must relate to:

- The supplied case
- The analysis
- Relevant medical concepts
- The selected difficulty and examination style

### FR-MCQ-03 — MCQ Structure — P0

Each MCQ must contain:

- Unique identifier
- Question stem
- Four or five answer options
- One correct answer
- Explanation
- Learning objective

### FR-MCQ-04 — MCQ Response Shape — P0

The expected logical structure is:

```json
{
  "mcqs": [
    {
      "id": "string",
      "stem": "string",
      "options": [
        {
          "id": "A",
          "text": "string"
        }
      ],
      "correctOptionId": "A",
      "explanation": "string",
      "learningObjective": "string"
    }
  ]
}
```

### FR-MCQ-05 — One Correct Answer — P0

Each MCQ must have exactly one correct option.

### FR-MCQ-06 — No Trivial Repetition — P0

The MCQ set must not consist only of questions that repeat the leading diagnosis.

The set should include a mix of:

- Diagnostic reasoning
- Differential diagnosis
- Interpretation of findings
- Red flags
- Relevant basic or clinical concepts

### FR-MCQ-07 — Practice Mode — P0

The user must be able to:

- Select an answer
- Submit or reveal the answer
- See whether the answer is correct
- Read the explanation
- Continue to the next question

### FR-MCQ-08 — Progress — P0

The interface must show current question and total questions.

### FR-MCQ-09 — Score — P0

At completion, the application must show:

- Number correct
- Total questions
- Percentage score

The score is for self-study and must not be described as a validated exam prediction.

### FR-MCQ-10 — Review — P1

The user should be able to review all questions, selected answers and explanations after completion.

### FR-MCQ-11 — Copy and Print — P1

The user should be able to copy or print the MCQ set with answers and explanations.

---

# 10.8 Recent Local Cases

### FR-HISTORY-01 — Local Storage — P1

Completed analyses may be saved in browser localStorage.

### FR-HISTORY-02 — No Cloud Claim — P0

The interface must not imply that recent cases are securely synchronized or backed up.

### FR-HISTORY-03 — Stored Fields — P1

A local record may include:

- Local identifier
- Created date and time
- Short generated title
- Original case text
- Selected configuration
- Validated analysis
- Generated MCQs where available

### FR-HISTORY-04 — Maximum Records — P1

The application should retain no more than 20 recent cases.

When the limit is exceeded, the oldest record may be removed.

### FR-HISTORY-05 — Reopen — P1

The user must be able to reopen a stored case.

### FR-HISTORY-06 — Delete One — P1

The user must be able to delete one stored case.

### FR-HISTORY-07 — Clear All — P1

The user must be able to clear all recent cases after confirmation.

### FR-HISTORY-08 — Storage Failure — P1

If localStorage is unavailable or full, the current analysis must remain usable and the application must show a non-blocking warning.

---

# 10.9 Copy and Print

### FR-EXPORT-01 — Copy Feedback — P0

After copying, the interface must provide visible success or failure feedback.

### FR-EXPORT-02 — Print Analysis — P0

The user must be able to print the analysis or save it as PDF through the browser print dialog.

### FR-EXPORT-03 — Print Layout — P0

The print view must:

- Include CaseLens AI identity
- Include the submitted educational case
- Include all analysis sections
- Include the educational disclaimer
- Exclude navigation, buttons and loading controls
- Remain readable in portrait format

---

# 10.10 Navigation

### FR-NAV-01 — Primary Navigation — P0

The application must provide clear access to:

- New Case
- Current Analysis when available
- Recent Cases
- About and Safety

### FR-NAV-02 — State Protection — P0

Navigation away from unsaved input should either preserve the text or warn the user before discarding it.

### FR-NAV-03 — Browser Navigation — P0

Browser back and forward behavior must not create broken or misleading application state.

---

# 10.11 About, Safety and Privacy

### FR-SAFETY-01 — Educational Purpose — P0

The About view must explain that CaseLens AI is an educational tool for medical learners.

### FR-SAFETY-02 — Limitations — P0

The application must disclose that AI output may be incomplete or incorrect and should be independently verified.

### FR-SAFETY-03 — Patient Information — P0

The application must tell users not to enter identifiable patient information.

### FR-SAFETY-04 — Data Handling — P0

The application must explain:

- Cases are sent to Gemini for processing
- Recent history is stored locally when enabled
- The MVP does not provide a cloud patient-record system
- Raw case text must not be intentionally stored in application logs

### FR-SAFETY-05 — No Emergency Use — P0

The application must clearly state that it must not be used for emergency medical decisions.

---

## 11. Error Requirements

### ER-01 — Validation Error — P0

Validation errors must identify what needs correction without deleting the user’s input.

### ER-02 — Network Error — P0

The application must explain that the request could not reach the service and provide retry behavior.

### ER-03 — Gemini Error — P0

Provider failures must be translated into a useful application message without exposing provider secrets or internal stack traces.

### ER-04 — Timeout — P0

Timeout errors must preserve input and allow retry.

### ER-05 — Invalid AI Output — P0

Malformed output must be treated as failure, not partial success.

### ER-06 — Rate Limit — P1

When the service is rate-limited, the user should receive a clear message and guidance to retry later.

### ER-07 — Unknown Error — P0

Unexpected errors must show a safe generic message and a recovery path.

### ER-08 — No False Success — P0

The interface must never show a completed analysis or successful copy, save or submission state unless the operation actually succeeded.

---

## 12. Non-Functional Requirements

# 12.1 Performance

### NFR-PERF-01 — Initial Load — P0

The primary case-entry interface should become usable promptly on a typical mobile connection.

### NFR-PERF-02 — Essential Content First — P0

Application identity, safety notice, input and primary action must load before non-essential decoration.

### NFR-PERF-03 — Responsive Interaction — P0

Buttons and controls must acknowledge interaction immediately.

### NFR-PERF-04 — No Artificial Delay — P0

The application must not add fake waiting time to make AI processing appear more sophisticated.

---

# 12.2 Accessibility

### NFR-ACCESS-01 — Keyboard Use — P0

All essential functions must be operable using a keyboard.

### NFR-ACCESS-02 — Visible Focus — P0

Interactive elements must show visible keyboard focus.

### NFR-ACCESS-03 — Labels — P0

Inputs and controls must have visible and programmatic labels.

### NFR-ACCESS-04 — Status Announcements — P0

Loading, success and error messages must be available to assistive technology.

### NFR-ACCESS-05 — Contrast — P0

Text and essential controls must meet appropriate contrast requirements.

### NFR-ACCESS-06 — Reduced Motion — P1

Any non-essential motion must respect reduced-motion preferences.

---

# 12.3 Responsive Design

### NFR-RESP-01 — Minimum Width — P0

The primary workflow must remain usable from approximately 320 CSS pixels upward.

### NFR-RESP-02 — No Horizontal Overflow — P0

Principal views must not introduce unintended horizontal scrolling.

### NFR-RESP-03 — Mobile Reading — P0

Analysis sections and MCQs must remain readable without desktop-only layouts.

### NFR-RESP-04 — Touch Targets — P0

Buttons and answer options must be comfortably usable on touch devices.

---

# 12.4 Security

### NFR-SEC-01 — Server-Side Gemini Request — P0

Gemini API calls must occur through server-side code.

### NFR-SEC-02 — Secret Protection — P0

The Gemini API key must not appear in:

- Client code
- Browser responses
- Public source history
- README
- Screenshots

### NFR-SEC-03 — Environment Variables — P0

Secrets must be stored using local environment variables and Vercel environment configuration.

### NFR-SEC-04 — Safe Errors — P0

Production errors must not expose stack traces, environment values or provider credentials.

### NFR-SEC-05 — Input Size — P0

Input size must be limited server-side as well as client-side.

### NFR-SEC-06 — Rate Protection — P1

The server route should include reasonable abuse or rate protection if practical within the deadline.

---

# 12.5 Privacy

### NFR-PRIV-01 — No Raw Case Logs — P0

Application logging must not intentionally include complete submitted case text.

### NFR-PRIV-02 — Minimal Telemetry — P0

If analytics are added, raw case content and AI output must not be sent as analytics parameters.

### NFR-PRIV-03 — Local History Control — P1

Users must be able to delete locally stored cases.

### NFR-PRIV-04 — Clear Disclosure — P0

The privacy explanation must accurately describe actual data handling.

---

# 12.6 Reliability

### NFR-REL-01 — Consistent Validation — P0

The same input rules must be enforced on client and server where applicable.

### NFR-REL-02 — Retry Safety — P0

Retrying a failed request must not corrupt the current case or history.

### NFR-REL-03 — Schema Enforcement — P0

Only schema-valid AI output may enter application state.

### NFR-REL-04 — Production Verification — P0

The full workflow must be tested against the public Vercel deployment, not only locally.

---

## 13. Data Model

The MVP requires no remote database.

### 13.1 Runtime Case Request

```text
caseText
selectedDifficulty
selectedExamStyle
requestedMcqCount
```

### 13.2 Validated Analysis

Stored in application memory and optionally localStorage according to the response contract.

### 13.3 Local Case Record

```ts
interface LocalCaseRecord {
  id: string;
  createdAt: string;
  title: string;
  caseText: string;
  difficulty: 'basic' | 'intermediate' | 'advanced';
  examStyle: 'general' | 'nre' | 'usmle' | 'plab' | 'mrcp';
  requestedMcqCount: 3 | 5 | 10;
  analysis: CaseAnalysis;
  mcqs?: GeneratedMcq[];
}
```

Local interfaces are illustrative and may be refined during implementation without changing product behavior.

---

## 14. API Requirements

### API-01 — Analysis Endpoint — P0

Recommended route:

```text
POST /api/analyse
```

Request:

```json
{
  "caseText": "string",
  "difficulty": "basic | intermediate | advanced",
  "examStyle": "general | nre | usmle | plab | mrcp"
}
```

Success response:

```json
{
  "success": true,
  "analysis": {}
}
```

Failure response:

```json
{
  "success": false,
  "error": {
    "code": "string",
    "message": "string"
  }
}
```

### API-02 — MCQ Endpoint — P0

Recommended route:

```text
POST /api/mcqs
```

Request includes:

- Original case
- Validated analysis summary or approved relevant fields
- Difficulty
- Examination style
- Quantity

### API-03 — Method Restrictions — P0

Unsupported HTTP methods must return an appropriate response.

### API-04 — Validation — P0

Every request must be validated server-side before contacting Gemini.

### API-05 — Error Codes — P0

Recommended application error codes include:

```text
INVALID_INPUT
INPUT_TOO_LONG
NON_MEDICAL_INPUT
AI_TIMEOUT
AI_RATE_LIMITED
AI_PROVIDER_ERROR
AI_INVALID_RESPONSE
INTERNAL_ERROR
```

---

## 15. System Prompt Requirements

### PR-AI-01 — Role

The system prompt must define Gemini as an educational clinical-reasoning assistant for medical learners.

### PR-AI-02 — Supplied Information

The model must treat the submitted case as the only source of patient-specific facts.

### PR-AI-03 — No Fabrication

The model must not invent:

- Symptoms
- Examination findings
- Laboratory values
- Imaging findings
- Medical history
- Medications
- Demographics

### PR-AI-04 — Facts and Inference

The model must clearly separate supplied facts from inference.

### PR-AI-05 — Calibrated Certainty

The model must avoid confirmed-diagnosis language unless the educational case explicitly includes definitive evidence.

### PR-AI-06 — Insufficient Information

The model must state when the case cannot support a confident interpretation.

### PR-AI-07 — Medical Boundary

The model must not provide patient-specific treatment, prescriptions or emergency-management instructions.

### PR-AI-08 — Red Flags

The model may identify educational red flags but must not imply that the application has clinically assessed a real patient.

### PR-AI-09 — Structured Output

The model must return only the requested response structure.

### PR-AI-10 — MCQ Quality

MCQs must have one best answer, plausible distractors and clear explanations.

The complete prompt language will be defined in the later AI Feature and Prompt Specification.

---

## 16. Visual and Interaction Requirements

### UI-01 — Tone

The interface should feel:

- Calm
- Focused
- Academic
- Modern
- Trustworthy
- Easy to read

It must not resemble:

- A hospital-management dashboard
- A general chatbot clone
- A course marketplace
- An entertainment quiz application

### UI-02 — Content Hierarchy

The case input and generated analysis must remain the visual priority.

### UI-03 — Analysis Sections

Analysis sections should use clear headings and progressive reading order.

### UI-04 — Medical Color Use

Color may support status and hierarchy but must not imply clinical certainty or replace text labels.

### UI-05 — Loading

Loading states should be restrained and informative.

### UI-06 — Empty States

History and analysis views must explain what the user should do when no data exists.

The detailed screen specification will be defined in User Flows and Information Architecture and the Stitch Design Brief.

---

## 17. Acceptance Criteria

### AC-PRD-01 — Complete Input-to-Analysis Workflow

A user can enter a valid educational case and receive a schema-valid structured analysis through the public application.

### AC-PRD-02 — Empty Input

Empty submission is rejected with a clear message and no Gemini request.

### AC-PRD-03 — Short or Insufficient Input

The system requests more information or returns an explicitly uncertain analysis without fabricating facts.

### AC-PRD-04 — Non-Medical Input

Clearly non-medical input does not produce fabricated clinical analysis.

### AC-PRD-05 — Fact Separation

Supplied facts are visually separated from AI interpretation.

### AC-PRD-06 — No Invented Findings

Defined test cases show that the application does not present missing data as supplied fact.

### AC-PRD-07 — Differential Diagnosis

A valid analysis can contain reasonable alternatives with supporting and opposing evidence.

### AC-PRD-08 — Red Flags

The red-flag section accurately reflects the supplied case and retains the educational boundary.

### AC-PRD-09 — MCQ Generation

The application generates the selected quantity of schema-valid MCQs.

### AC-PRD-10 — MCQ Practice

A user can answer questions, view explanations and receive a final score.

### AC-PRD-11 — API Failure

Network, timeout and provider failures preserve case input and show a retry path.

### AC-PRD-12 — Invalid AI Response

Malformed AI output is rejected and never displayed as a successful analysis.

### AC-PRD-13 — Duplicate Submission

Repeated clicks do not create uncontrolled duplicate requests.

### AC-PRD-14 — Local History

When enabled, a completed case can be stored, reopened and deleted locally.

### AC-PRD-15 — Copy

The user can copy the complete analysis and receives accurate feedback.

### AC-PRD-16 — Print

The user can print a readable analysis without unnecessary interface controls.

### AC-PRD-17 — Mobile

The full input, analysis and MCQ journey works at a representative mobile width.

### AC-PRD-18 — Keyboard

The full primary journey can be completed using keyboard controls.

### AC-PRD-19 — Secret Protection

No Gemini key appears in the public repository or client-side bundle.

### AC-PRD-20 — Production

The exact production deployment successfully completes the real Gemini workflow.

---

## 18. Minimum Test Scenarios

The formal Testing and Acceptance Criteria document must include at least:

- Normal complete medical case
- Ambiguous case
- Insufficient case
- Empty input
- Whitespace input
- Very short input
- Maximum-length input
- Non-medical input
- Input containing identifiable patient information
- Repeated submission
- Gemini timeout
- Gemini provider error
- Rate limit
- Invalid JSON response
- Schema-valid but empty response fields
- Local-storage unavailable
- Copy failure
- Print layout
- Mobile layout
- Keyboard navigation
- Reduced-motion behavior
- Public deployment workflow

---

## 19. Release Gate

The product may be declared complete only when:

1. Every P0 requirement is implemented.
2. Every P0 acceptance criterion passes against the latest code.
3. The application is available at a public URL.
4. The real Gemini workflow works in production.
5. The repository is public.
6. The README fully reports the project.
7. No API key or patient information is exposed.
8. No known submission-blocking issue remains.

P1 features may be deferred only when their absence is documented honestly in the README.

---

## 20. Traceability to Course Evaluation

| Course criterion | Product evidence |
|---|---|
| Idea | Structured clinical-reasoning workflow, fact/inference separation, case-based MCQs |
| Completion | End-to-end input, analysis, MCQs, error handling, responsive interface |
| Deployment | Public Vercel URL with working Gemini integration |
| Reporting | Comprehensive README, screenshots, setup, architecture, testing and limitations |

---

## 21. Dependencies

The MVP depends on:

- Gemini API access
- Valid Gemini API key
- GitHub repository access
- Vercel account and deployment access
- Stable Next.js-compatible runtime
- Final approved system prompt
- Approved UI design
- Sufficient time for production testing before 27 July 2026

---

## 22. Risks and Controls

### RISK-01 — Scope Expansion

**Risk:** The application grows into an LMS or patient system.  
**Control:** Enforce P0/P1/P2 boundaries and require requirement traceability.

### RISK-02 — Hallucinated Findings

**Risk:** Gemini invents missing case data.  
**Control:** Strict prompt, structured schema and adversarial tests.

### RISK-03 — Unsafe Medical Output

**Risk:** Output appears to diagnose or treat a real patient.  
**Control:** Educational framing, prompt rules and visible disclaimers.

### RISK-04 — Invalid AI Structure

**Risk:** Gemini returns malformed or incomplete data.  
**Control:** Schema validation and safe retry behavior.

### RISK-05 — Secret Exposure

**Risk:** API key enters the public repository or client bundle.  
**Control:** Server-side routes, environment variables and repository scanning.

### RISK-06 — Deployment Failure

**Risk:** Local application works but production does not.  
**Control:** Deploy early and test the exact production environment.

### RISK-07 — README Neglect

**Risk:** Working software loses marks because reporting is incomplete.  
**Control:** Update README throughout implementation and audit it before submission.

---

## 23. Document Status

**Requirements defined:** Yes  
**Implementation started:** No  
**Production evidence available:** No  
**Current status:** Proposed for approval  
**Next document:** Assignment Traceability Matrix
