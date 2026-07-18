# CaseLens AI

## Verified Google Stitch Design Brief

### Document Control

**Version:** 1.0  
**Status:** Ready for Stitch Input  
**Date:** 18 July 2026  
**Design phase:** Phase 2  
**Approved source baseline:** Phase 1 v1.1

---

## 1. Design Assignment

Design a responsive AI-powered medical-learning web application named **CaseLens AI**.

CaseLens AI helps medical students and examination candidates practise structured clinical reasoning. A learner enters an educational clinical case, receives validated structured analysis, generates case-specific MCQs, attempts those questions, and revisits recent cases stored locally in the browser.

This is an interactive application, not a marketing website.

---

## 2. Primary User Outcome

The learner should be able to move confidently through this sequence:

```text
Enter case
→ Configure analysis
→ Submit
→ Review structured reasoning
→ Generate MCQs
→ Attempt and review questions
→ Revisit the case later
```

The design should reduce cognitive load and make the distinction between facts, interpretation, uncertainty, red flags, and revision material immediately understandable.

---

## 3. Target Users

Primary users:

- MBBS students
- NRE candidates
- USMLE candidates
- PLAB candidates
- MRCP candidates
- Medical learners practising case-based reasoning

Users may work on mobile phones, tablets, laptops, and desktop computers.

The interface must not assume that users are clinicians managing real patients.

---

## 4. Product Boundaries

Do not include:

- Login or registration
- User profiles
- Patient records
- Hospital navigation
- Appointments
- Prescriptions
- Treatment plans
- Medical-image upload
- Course administration
- Teacher dashboards
- Attendance
- Certificates
- Payments
- Social feeds
- Chat transcripts
- Fake analytics
- Official exam-body branding

Do not use language suggesting diagnosis or treatment of a real patient.

---

## 5. Required Navigation

Desktop primary navigation:

- New Case
- Recent Cases
- About & Safety

Recommended desktop shell:

- Compact top header
- CaseLens AI wordmark or simple text identity on the left
- Primary navigation on the right or centre
- Main content area with a readable maximum width
- No persistent administrative sidebar

Recommended mobile shell:

- Compact header with product identity
- Bottom navigation or a concise menu containing the same three destinations
- Primary actions remain reachable without awkward horizontal scrolling

---

## 6. Visual Direction

Use the **Clinical Workspace** direction.

The interface should feel:

- Calm
- Focused
- Trustworthy
- Modern
- Educational
- Precise
- Lightweight

It should not feel:

- Sterile
- Corporate-healthcare bureaucratic
- Futuristic
- Gamified like a children’s quiz
- Like a generic AI chatbot
- Like an electronic medical record

### Suggested Colour System

Use this as a starting point, adjusting only for accessibility:

- Background: `#F5F7FA`
- Surface: `#FFFFFF`
- Primary text: `#152238`
- Secondary text: `#5B6678`
- Border: `#D9E0E8`
- Primary action: `#0F766E`
- Primary hover: `#0B5F59`
- Primary soft surface: `#E7F4F2`
- Informational accent: `#2563EB`
- Success: `#027A48`
- Warning: `#B54708`
- Danger / red flag: `#B42318`

Avoid purple AI gradients, glowing effects, and excessive colour coding.

### Typography

Use a clear sans-serif family suitable for application interfaces, such as Geist, Inter, or a similar modern system font.

Suggested hierarchy:

- Page title: 28–36 px desktop, 24–30 px mobile
- Section title: 18–22 px
- Body: 15–17 px
- Supporting labels: 13–14 px
- Minimum normal text: 14 px

Use comfortable line height and avoid overly wide reading columns.

### Shape and Spacing

- Moderate corner radius, approximately 10–14 px
- Subtle borders rather than heavy shadows
- Shadows only where elevation clarifies interaction
- 8-point spacing system
- Minimum 44 by 44 px interactive targets
- Clear focus rings

---

## 7. Screen 1 — New Case Workspace

### Purpose

Allow the learner to begin immediately.

### Required Content

- CaseLens AI identity
- Short statement: “Practise structured clinical reasoning from educational cases.”
- Educational-use notice
- Privacy warning not to enter identifiable patient information
- Large case-input field
- Helpful placeholder showing the type of educational case expected
- Difficulty selector: Basic, Intermediate, Advanced
- Examination-style selector: General, NRE, USMLE, PLAB, MRCP
- MCQ-count selector: 3, 5, 10
- Primary button: **Analyse Case**
- Optional action to load one clearly labelled sample case
- Link or compact note explaining how the analysis works

### Layout Guidance

Desktop:

- Centred workspace, approximately 900–1100 px maximum width
- Main case editor is visually dominant
- Configuration controls appear beneath or beside the editor without competing with it
- Privacy and educational messages are concise

Mobile:

- Single-column layout
- Case editor remains large enough for practical input
- Selectors stack cleanly
- Primary action spans the available width

### Required States

- Empty
- Focused input
- Inline validation error
- Submitting / loading
- Provider failure with retry

---

## 8. Screen 2 — Analysis Loading State

### Purpose

Show that analysis is in progress while preventing duplicate submission.

### Requirements

- Preserve visible case context or summary
- Display a calm progress message such as “Structuring the case analysis…”
- Show skeletons representing expected analysis sections
- Disable duplicate submission
- Do not show a fake percentage
- Provide safe navigation back only if it will not create duplicate requests
- Keep educational-use wording visible but secondary

Do not use animated medical scans, heartbeat monitors, or diagnostic theatre.

---

## 9. Screen 3 — Case Analysis Workspace

### Purpose

Present structured AI analysis in a readable learning sequence.

### Required Header Area

- Generated short case title
- Date or local timestamp
- Difficulty
- Examination style
- Analysis status
- Actions: Copy All, Print / Save PDF, New Case
- Primary next action: **Generate MCQs**

### Required Analysis Sections

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

### Presentation Guidance

- Use a clear section navigation or anchored contents list on desktop
- Use stacked cards or accordions on mobile
- Facts and reasoning must look visually different
- Diagnosis confidence may use text labels such as Low, Moderate, or High, but never a dramatic certainty gauge
- Differential diagnoses should support comparison through structured rows or cards
- Red flags use restrained danger styling and non-colour cues
- Missing information should feel actionable for learning, not like a system error
- Every section may have an individual copy action

### Empty or Conditional Content

- `mostLikelyDiagnosis` may be absent
- Red flags may be empty
- Negative findings may be empty
- The design must handle empty sections gracefully without inventing content

---

## 10. Screen 4 — Insufficient Information State

### Purpose

Explain that a definitive analysis is not justified while preserving educational value.

### Requirements

- Clear heading: “More information is needed”
- Show supplied facts that could be extracted
- Show why certainty is limited
- Prominently list missing information
- Show a low-confidence possibility only if one exists
- Provide **Edit Case** and **Start New Case** actions
- MCQ generation may be disabled or clearly limited
- Avoid red error styling because this is a valid analytical outcome, not a technical failure

---

## 11. Screen 5 — MCQ Practice Workspace

### Purpose

Allow focused case-specific question practice.

### Required Content

- Case title or context label
- Question progress, for example “Question 2 of 5”
- Question stem
- Four options labelled A, B, C, D
- Single-answer selection
- Primary action: **Check Answer**
- After answer submission:
  - Correct or incorrect status
  - Correct answer
  - Explanation
  - Learning objective
  - Optional distractor explanations
  - **Next Question** action

### Interaction Rules

- Do not show the correct answer before submission
- After checking, lock the current selection for that attempt
- Correctness must use text and iconography, not colour alone
- Keep navigation focused; do not show all questions simultaneously by default
- Preserve the relationship to the original case

### Mobile

- Options use large touch targets
- Explanation remains readable without horizontal scrolling
- Primary action remains visible after selection

---

## 12. Screen 6 — MCQ Completion State

### Required Content

- Score: correct answers, total questions, percentage
- Neutral wording stating that the score is for self-study, not an exam prediction
- Review Questions action
- Return to Case Analysis action
- Start New Case action
- Concise summary of learning objectives covered

Avoid celebratory confetti, ranking badges, streaks, or fabricated mastery claims.

---

## 13. Screen 7 — Recent Cases

### Purpose

Show locally stored case analyses.

### Each Case Item Shows

- Safe generated title
- Date and time
- Examination style
- Analysis status
- MCQ status
- Reopen action
- Delete action

### Page Actions

- Start New Case
- Clear All History with confirmation

### Required Notice

“Recent cases are stored only in this browser and are not securely synchronised or backed up.”

### Empty State

- Short explanation
- Start a New Case action
- No fake sample history

---

## 14. Screen 8 — About & Safety

### Required Sections

- What CaseLens AI does
- Who it is for
- How AI is used
- Educational-use limitation
- No-patient-data warning
- Local-storage explanation
- Known limitations
- Emergency and professional-evaluation boundary

Keep this page readable and concise. It should not resemble a legal wall generated to discourage comprehension.

---

## 15. Technical Error State

Create a reusable error component for:

- Network failure
- Provider timeout
- Provider unavailable
- Invalid AI response
- Rate limiting
- Local-storage failure

It must include:

- Plain-language title
- Brief explanation
- Appropriate retry or return action
- Preserved user input where possible
- No stack traces, secret details, or alarming clinical language

---

## 16. Accessibility Requirements

The visual design must support:

- WCAG AA contrast targets
- Keyboard navigation
- Visible focus states
- Form labels outside placeholders
- Accessible error association
- Status text beyond colour
- Logical heading order
- 44 by 44 px touch targets
- Reduced-motion compatibility
- Screen-reader-friendly progress and result messages

---

## 17. Responsive Requirements

Generate references at minimum for:

- Desktop: approximately 1440 px wide
- Mobile: approximately 390 px wide

Tablet should be derivable from the system.

Mobile must preserve:

- Primary workflow order
- Section hierarchy
- Action visibility
- Error recovery
- MCQ readability
- History management

---

## 18. Required Stitch Output

Generate a consistent design system and the following references:

### Desktop

1. New Case workspace
2. Loading state
3. Analysis workspace
4. Insufficient-information result
5. MCQ practice
6. MCQ completion
7. Recent Cases
8. About & Safety
9. Technical error state

### Mobile

1. New Case
2. Analysis workspace
3. MCQ practice
4. Recent Cases
5. Primary error state

Use reusable components and consistent tokens across every screen.

---

## 19. Rejection Conditions

Reject generated designs that include:

- A large promotional hero before the application
- Generic chat bubbles
- Patient identity fields
- Hospital-dashboard navigation
- Login or subscription prompts
- Fake medical charts
- Fake AI confidence meters
- Glowing brain imagery
- Tiny low-contrast text
- Missing error, loading, or empty states
- Desktop-only layouts
- Unsupported features
- Inconsistent navigation
- Different design systems on different screens

---

## 20. Stitch Prompt Summary

Use the following compact prompt when the full brief cannot be inserted directly:

> Design a responsive medical-learning web application named CaseLens AI. It is a focused clinical-reasoning workspace, not a marketing site, chatbot, LMS, hospital dashboard, or patient-record system. Create desktop and mobile screens for New Case, loading, structured case analysis, insufficient information, MCQ practice, MCQ completion, Recent Cases, About & Safety, and technical errors. Use a calm light Clinical Workspace style with deep navy text, restrained teal actions, accessible status colours, structured cards, progressive disclosure, minimal navigation, and no AI clichés. The main journey is enter case → analyse → review reasoning → generate MCQs → attempt questions → revisit locally. Include privacy warnings, educational boundaries, local-storage messaging, accessible states, and practical responsive layouts.
