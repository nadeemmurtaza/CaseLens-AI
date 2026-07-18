# CaseLens AI

## User Flows and Information Architecture

### Document Control

**Project:** CaseLens AI  
**Document:** User Flows and Information Architecture  
**Version:** 1.0  
**Status:** Proposed for Approval  
**Date:** 18 July 2026  
**Primary Users:** Medical students and examination candidates  

---

## 1. Purpose

This document defines how users move through CaseLens AI, which screens and routes exist, what each view must contain, and how loading, empty, success, and failure states behave.

The application must feel like one coherent clinical-reasoning workspace. It must not resemble a marketing website, hospital-management dashboard, generic chatbot, or miniature LMS assembled because somebody discovered a sidebar component.

---

## 2. Information Architecture Principles

### IA-01: Application First

The first useful screen must let the learner begin a case. A long promotional homepage is not required.

### IA-02: One Primary Journey

The principal journey is:

```text
New case
→ Validate
→ Analyse
→ Review reasoning
→ Generate MCQs
→ Attempt and review
→ Copy, print, or revisit locally
```

### IA-03: Minimal Navigation

Primary navigation contains only:

- New Case
- Recent Cases
- About & Safety

### IA-04: Results Remain Connected to the Case

Analysis, MCQs, and revision actions must remain linked to the same locally stored case record.

### IA-05: Progressive Disclosure

The interface should reveal detail in readable sections. It should not place the full prompt, all analysis sections, all MCQs, history, and safety text into one heroic page of vertical punishment.

### IA-06: Mobile Reading Order

Mobile layouts must follow the same logical order as desktop without relying on side-by-side panels.

### IA-07: No Account Dependency

No journey may require registration or login.

---

## 3. Proposed Route Map

| Route | View | Purpose | Access |
|---|---|---|---|
| `/` | New Case Workspace | Enter and configure a case | Public |
| `/cases/[caseId]` | Case Analysis Workspace | Review saved analysis and access MCQs | Public, local record required |
| `/cases/[caseId]/mcqs` | MCQ Practice | Attempt case-specific questions | Public, local record required |
| `/history` | Recent Cases | Reopen or delete locally stored cases | Public |
| `/about` | About & Safety | Explain purpose, AI use, privacy, and limitations | Public |
| `/not-found` or framework default | Not Found | Recover from invalid routes | Public |

`caseId` is a locally generated identifier. It is not a patient record number and must not contain user-entered medical text.

---

## 4. Application Shell

The application shell must contain:

- CaseLens AI identity
- Primary navigation
- Main content region
- Visible educational boundary where appropriate
- Mobile navigation behavior
- Connection or request status only when relevant

The shell must not contain:

- Course administration
- User profile controls
- Billing
- Notifications unrelated to the active case
- Hospital or patient-management navigation
- Fake analytics

---

## 5. Primary User Flow: Analyse a Case

### Entry Conditions

- User opens `/`.
- No authentication is required.
- Case input is empty unless an example is intentionally loaded.

### Main Flow

1. User reads the short product explanation and no-patient-data warning.
2. User enters or pastes an educational case.
3. User optionally selects difficulty, examination style, and MCQ quantity.
4. User selects **Analyse Case**.
5. Client-side validation runs.
6. If valid, the application submits the case once to the server route.
7. The interface enters a loading state and disables duplicate submission.
8. The server validates the request.
9. The server calls Gemini.
10. The provider response is parsed and validated against the analysis schema.
11. A local case record is created.
12. The user is taken to `/cases/[caseId]`.
13. The structured analysis is displayed.

### Success Outcome

The learner can review the case summary, supplied facts, findings, diagnosis reasoning, differentials, missing information, red flags, study topics, and educational disclaimer.

### Alternate Flows

#### Empty Input

- Submission is stopped before API use.
- The case field receives focus.
- The user sees a clear instruction to enter a case.

#### Too-Short or Meaningless Input

- Submission is rejected.
- The error explains that more medically relevant information is required.

#### Non-Medical Input

- The application explains that CaseLens AI analyses educational medical cases.
- No diagnosis is generated.

#### Network or Provider Failure

- The original case text remains available.
- The user receives a useful error.
- A retry action may be offered when safe.
- No false local success record is created.

#### Invalid Gemini Output

- The response is not displayed as valid analysis.
- The user sees a processing error.
- The case input is preserved.

---

## 6. Secondary User Flow: Generate and Attempt MCQs

### Entry Conditions

- A valid local case record exists.
- Structured analysis has been completed.

### Main Flow

1. User selects **Generate MCQs** from the analysis workspace.
2. The application checks whether valid MCQs already exist for the current case and configuration.
3. If not, it sends the case and validated analysis context to the server route.
4. The server requests structured MCQs from Gemini.
5. The response is validated.
6. MCQs are saved inside the local case record.
7. The user enters `/cases/[caseId]/mcqs`.
8. The first question is shown.
9. The user selects one option.
10. The user submits or reveals the answer.
11. The interface shows correctness, explanation, and learning objective.
12. The user moves to the next question.
13. At completion, the application shows score and review options.

### MCQ Interaction Rules

- One answer may be selected per question.
- The correct answer must not appear before answer submission.
- After reveal, the selection becomes read-only for that attempt.
- The explanation must remain visible when reviewing.
- Progress must be clear.
- Leaving and returning may preserve the current attempt locally where practical.

### Alternate Flows

#### MCQ Generation Failure

- Existing case analysis remains intact.
- The user receives a targeted error.
- The user may retry safely.

#### Invalid MCQ Structure

- Invalid questions are not shown.
- The request fails as a set unless the implementation can safely validate and retain only complete questions without changing the requested count.

#### Existing MCQs

- The application may reopen the stored set rather than consume another provider request.
- A later regeneration action must be explicit.

---

## 7. Secondary User Flow: Recent Cases

### Main Flow

1. User opens `/history`.
2. The application reads the local history index.
3. Cases are ordered by most recent activity.
4. Each item shows only safe summary information:
   - Case title or generated short label
   - Date and time
   - Examination style
   - Analysis status
   - MCQ status
5. User may reopen a case.
6. User may delete one case after confirmation.
7. User may clear all history after stronger confirmation.

### Empty State

The page explains that analysed cases stored on this device will appear here and provides a **Start a New Case** action.

### Storage Failure

If local storage is unavailable:

- The page explains that recent-case storage is unavailable.
- The main AI workflow remains usable when possible.
- The application does not claim that a case was saved.

---

## 8. Secondary User Flow: Copy Analysis

1. User opens a case analysis.
2. User selects copy for one section or the complete analysis.
3. The application creates readable plain text or structured Markdown.
4. Clipboard write is attempted.
5. Success is announced accessibly.
6. Failure provides a useful manual alternative.

Copied content must include the educational boundary when the complete analysis is copied.

---

## 9. Secondary User Flow: Print or Save as PDF

1. User opens analysis or MCQs.
2. User selects **Print / Save PDF**.
3. Print-specific styles remove navigation and interactive controls.
4. The printed content includes:
   - Case label
   - Analysis or MCQ content
   - Date
   - Educational disclaimer
5. Browser print dialogue opens.

The application itself does not need to generate or store a server-side PDF for the MVP.

---

## 10. About and Safety Flow

The `/about` view must explain:

- What CaseLens AI does
- Who it is for
- How Gemini is used
- Why outputs may be imperfect
- The distinction between education and patient care
- The prohibition on identifiable patient information
- Local history behavior
- Data not intentionally retained by the application server
- How users should respond to real medical emergencies

The page must not imply medical-device certification, diagnostic approval, or professional endorsement.

---

## 11. Screen Specifications

### 11.1 New Case Workspace

#### User Objective

Submit an educational case with minimal friction.

#### Required Content

- Product title
- One-sentence purpose
- Educational-use notice
- No-identifiable-patient-data warning
- Case text area
- Difficulty selection
- Examination-style selection
- MCQ quantity selection
- Analyse Case action
- Optional example-case action

#### Required States

- Empty
- Editing
- Validation error
- Ready
- Submitting
- Request failure

#### Primary Action

**Analyse Case**

#### Forbidden Elements

- Open-ended chat transcript
- Login requirement
- Course catalogue
- Patient identity fields
- Decorative dashboard metrics

---

### 11.2 Analysis Loading State

#### User Objective

Understand that the request is being processed without losing control.

#### Required Content

- Clear status message
- Static explanation that analysis may take a moment
- Preserved case context or short label

#### Behavior

- Duplicate submission disabled
- No fake percentage
- No claim that specific stages completed unless they are real
- Timeout leads to a clear recoverable error

---

### 11.3 Case Analysis Workspace

#### User Objective

Understand the case through a structured reasoning sequence.

#### Required Sections

1. Case Summary
2. Supplied Facts
3. Important Positive Findings
4. Important Negative Findings
5. Most Likely Diagnosis or Insufficient Information
6. Clinical Reasoning
7. Differential Diagnoses
8. Missing Information
9. Red Flags
10. Recommended Study Topics
11. Educational Disclaimer

#### Required Actions

- Generate or open MCQs
- Copy full analysis
- Copy section
- Print / Save PDF
- Start new case
- Return to history
- Delete local case

#### Layout Guidance

- Sections may use accordions or grouped cards.
- Most likely diagnosis must not visually overpower uncertainty.
- Red flags require clear but non-alarmist presentation.
- The original case should remain viewable without dominating the analysis.

---

### 11.4 MCQ Practice

#### User Objective

Apply reasoning from the case and review explanations.

#### Required Content

- Question progress
- Question stem
- Options
- Submit answer action
- Correctness state after submission
- Explanation
- Learning objective
- Previous and next controls where applicable
- Final score summary

#### Required States

- Generating
- Ready
- Answer selected
- Answer revealed
- Complete
- Generation failure

---

### 11.5 Recent Cases

#### User Objective

Revisit or remove local learning records.

#### Required Content

- Local-storage explanation
- Case list
- Reopen action
- Delete action
- Clear-all action
- Empty state

---

### 11.6 About & Safety

#### User Objective

Understand purpose, limits, privacy, and responsible use.

#### Required Content

- Educational purpose
- AI limitations
- No-patient-data rule
- Local-storage explanation
- No server-retention intent
- Emergency and professional-care boundary
- Project and author information where appropriate

---

## 12. Navigation Rules

### Desktop

A compact header or side navigation may be used, but the main workspace must remain dominant.

### Mobile

Use a simple header and menu or bottom navigation. Navigation must not cover content or reduce the text area excessively.

### Active State

The current area must be identifiable without relying on color alone.

### Keyboard

All navigation and controls must be keyboard accessible with visible focus.

---

## 13. Local Data Model for Navigation

A local case record should contain at minimum:

```text
id
createdAt
updatedAt
caseText
caseLabel
difficulty
examStyle
mcqCount
analysisStatus
analysis
mcqStatus
mcqs
attemptState
schemaVersion
```

The interface must treat local data as untrusted when reading it. Invalid or outdated records must fail safely.

---

## 14. Global Application States

| State | Required behavior |
|---|---|
| Initial | Show ready case workspace |
| Offline before submission | Explain that AI analysis requires a connection |
| Loading | Preserve context and prevent duplicate action |
| Success | Display validated content and save locally |
| Recoverable failure | Preserve user input and allow safe retry |
| Unrecoverable local record | Explain corruption and offer deletion/new case |
| Storage unavailable | Continue without falsely claiming persistence |
| Route not found | Offer New Case and Recent Cases paths |

---

## 15. Accessibility and Content Rules

- Every field has a visible label.
- Errors are associated with the relevant field.
- Loading and success messages are announced to assistive technology.
- Heading hierarchy follows the reasoning structure.
- Icons never replace essential text labels without accessible names.
- Color is not the only status indicator.
- Touch targets are comfortably usable.
- Long medical terms wrap safely.
- Generated content remains selectable and readable at zoom.

---

## 16. Analytics Boundaries

If analytics are added later:

- Never send raw case text.
- Never send generated medical analysis.
- Never send clipboard content.
- Never send local case identifiers if they can reveal content.
- Track only coarse product events such as analysis success, error class, MCQ completion, and device category.

Analytics are not required for the MVP.

---

## 17. Flow Acceptance Criteria

### UF-AC-01

A first-time user can identify where to enter a case without opening another page.

### UF-AC-02

A valid case can move from `/` to a stored analysis route without account creation.

### UF-AC-03

A failed analysis does not erase the entered case.

### UF-AC-04

A completed case can open MCQ practice without re-entering the case.

### UF-AC-05

Recent cases can be reopened and deleted locally.

### UF-AC-06

An invalid local `caseId` produces a recoverable not-found state.

### UF-AC-07

Copy and print actions provide success or failure feedback.

### UF-AC-08

The complete primary journey works at 320 CSS pixels without unintended horizontal scrolling.

### UF-AC-09

Keyboard users can complete the primary journey.

### UF-AC-10

No screen requests identifiable patient information.

---

## 18. Current Status

**Route model defined:** Yes  
**Primary journey defined:** Yes  
**Failure paths defined:** Yes  
**Screen requirements defined:** Yes  
**Mobile and accessibility behavior defined:** Yes  
**Implemented:** No  
**Phase status:** Proposed for approval
