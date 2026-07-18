# CaseLens AI

## Google Stitch Generation Prompts

### Document Control

**Project:** CaseLens AI  
**Phase:** Phase 2 — Verified Design Preparation and Interface Direction  
**Document:** Stitch Generation Prompts  
**Version:** 1.0  
**Status:** Ready for Stitch Execution  
**Date:** 18 July 2026  
**Approved Design Direction:** Clinical Workspace  
**Source Baseline:** Approved Phase 1 documentation on `main`  

---

## 1. Purpose

This document provides the exact copy-ready prompts for generating the initial CaseLens AI screen set in Google Stitch.

The first generation batch contains:

### Desktop

1. New Case
2. Case Analysis
3. MCQ Practice

### Mobile

4. New Case
5. Case Analysis
6. MCQ Practice

The desktop screens must be generated first and treated as the structural reference. The mobile screens must adapt the same product hierarchy rather than inventing a separate interface.

---

## 2. Execution Rules

Use one prompt per screen.

Do not ask Stitch to generate all six screens in one unconstrained request. Generate them in the following order:

```text
Desktop New Case
→ Desktop Case Analysis
→ Desktop MCQ Practice
→ Mobile New Case
→ Mobile Case Analysis
→ Mobile MCQ Practice
```

For every generation:

- Use the same CaseLens AI identity.
- Use the Clinical Workspace direction.
- Preserve the same visual tokens and component language.
- Do not add authentication, profiles, dashboards, billing, chat bubbles, patient records, hospital controls, analytics, or unsupported features.
- Treat the output as a product application screen, not a marketing landing page.
- Keep all language educational and non-clinical.
- Use realistic placeholder case content, but do not include identifiable patient data.

---

## 3. Shared Visual Direction

Apply these rules to all six screens.

### Product character

CaseLens AI should feel:

- Calm
- Focused
- Trustworthy
- Educational
- Structured
- Modern without being decorative
- Appropriate for medical learners

It must not feel:

- Like a hospital administration system
- Like an electronic medical record
- Like a generic AI chatbot
- Like an LMS
- Like a marketing website
- Like a futuristic sci-fi dashboard

### Layout language

- Light neutral application background
- White or very light elevated surfaces
- Deep navy primary text
- Restrained teal for primary actions and selected states
- Muted gray for supporting copy
- Amber only for caution and insufficient-information states
- Red only for genuine errors or educational red-flag emphasis
- Clear borders with minimal shadow
- Moderate rounded corners
- Comfortable reading width
- Strong spacing rhythm
- No gradients
- No glow effects
- No glassmorphism
- No oversized illustrations
- No decorative medical stock photography

### Typography

- Clean sans-serif interface typeface
- Clear heading hierarchy
- Body text optimized for long clinical reasoning content
- Avoid tiny captions
- Avoid excessive bold text
- Use sentence case rather than all caps

### Application shell

Desktop shell:

- Compact top bar
- CaseLens AI wordmark or simple text identity on left
- Navigation on right or center: New Case, Recent Cases, About & Safety
- No login or avatar controls
- Main content centered within a generous desktop container

Mobile shell:

- Compact top app bar
- CaseLens AI identity
- Minimal menu or compact navigation trigger
- Main action must remain easy to reach
- No dense sidebars

### Accessibility

- Clear contrast
- Visible focus states
- Large click targets
- Labels above controls
- Do not rely on color alone
- Preserve a logical reading order
- Avoid text embedded in images

---

# 4. Prompt 1 — Desktop New Case

Copy the full prompt below into Google Stitch.

```text
Design a polished desktop application screen for CaseLens AI, an AI-powered medical-learning web application that helps medical students practise structured clinical reasoning from educational case text.

SCREEN: New Case workspace
VIEWPORT: Desktop, approximately 1440px wide
DESIGN DIRECTION: Clinical Workspace

The interface must feel calm, trustworthy, structured and educational. It must look like a focused learning application, not a hospital dashboard, patient record system, LMS, marketing website or chatbot.

Use a light neutral background, white surfaces, deep navy text, restrained teal primary actions, muted gray supporting text, subtle borders, moderate rounded corners and minimal shadows. Do not use gradients, glowing AI graphics, glassmorphism, stock medical photography or decorative illustrations.

APPLICATION SHELL
- Compact top navigation bar
- CaseLens AI identity on the left
- Navigation items: New Case, Recent Cases, About & Safety
- New Case is visibly active
- No login, avatar, billing, notifications or account controls

MAIN CONTENT
Create a centered application workspace with a clear page title:
“Analyse an educational clinical case”

Add a short supporting sentence:
“Enter a fictional, de-identified or educational case to practise structured clinical reasoning and generate case-specific MCQs.”

Place a visible but calm educational and privacy notice near the top:
“Educational use only. Do not enter names, CNIC numbers, record numbers, contact details or other identifiable patient information.”

PRIMARY INPUT SURFACE
Create one large case-entry panel containing:
- Label: Clinical case
- Large multiline textarea
- Placeholder example that begins with a realistic de-identified educational case, such as:
  “A 54-year-old man presents with 2 hours of crushing central chest pain radiating to the left arm...”
- Character or input guidance beneath the field
- Clear action to remove or clear entered text, but do not make it visually dominant

CONFIGURATION
Below or beside the textarea, include three clearly labelled controls:
1. Difficulty: Basic, Intermediate, Advanced
2. Examination style: General, NRE, USMLE, PLAB, MRCP
3. MCQ count: 3, 5, 10

Use native-looking segmented controls or select fields that are practical to build in Next.js and Tailwind. Do not invent unsupported configuration.

PRIMARY ACTION
Add a strong teal button labelled:
“Analyse Case”

The button should be the only dominant action.

SECONDARY SUPPORT
Include a subtle link or button for:
“Use example case”

Add a small note that recent cases are stored only in the browser on this device and are not securely synchronized or backed up.

LAYOUT
Use a balanced desktop layout. A two-column layout is acceptable only if the case-entry area remains dominant and configuration remains visually connected to it. Avoid excessive empty dashboard panels.

REQUIRED STATES IMPLIED BY DESIGN
- Empty form state
- Clear labels and helper text
- Duplicate submission prevention should be visually possible by disabling the Analyse Case button during loading

DO NOT INCLUDE
- Chat interface
- Patient profile
- Hospital identifiers
- Diagnosis output on this screen
- Analytics
- Course modules
- Teacher controls
- Account controls
- Payment features
- Medical-image upload
- Voice input

Generate one complete desktop screen only.
```

---

# 5. Prompt 2 — Desktop Case Analysis

Copy the full prompt below into Google Stitch.

```text
Design a polished desktop application screen for CaseLens AI, an AI-powered medical-learning web application for practising structured clinical reasoning.

SCREEN: Case Analysis workspace
VIEWPORT: Desktop, approximately 1440px wide
DESIGN DIRECTION: Clinical Workspace

The interface must feel calm, trustworthy, analytical and educational. It must not resemble a patient chart, hospital dashboard, generic AI chatbot or marketing page.

Use the same visual system as the CaseLens AI New Case screen: light neutral background, white content surfaces, deep navy text, restrained teal actions, subtle borders, moderate rounded corners, minimal shadow, no gradients and no decorative AI imagery.

APPLICATION SHELL
- Compact top navigation
- CaseLens AI identity
- Navigation: New Case, Recent Cases, About & Safety
- Keep the application context clear without adding account controls

PAGE HEADER
Show a concise generated case title such as:
“Acute central chest pain with autonomic symptoms”

Under the title, show compact metadata:
- Intermediate
- NRE style
- Analysed just now
- Stored locally on this device

Add top-level actions:
- New Case
- Copy Analysis
- Print / Save PDF

Use secondary button styling for these actions.

MAIN ANALYSIS STRUCTURE
Create a readable long-form analysis workspace using structured sections. The page must support substantial text without becoming a dense dashboard.

Use the following exact section order:
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

SECTION DESIGN
- Use clear section headings
- Use white panels or grouped sections with subtle borders
- Avoid placing every sentence in a separate card
- Use lists where appropriate
- Use restrained icons only when they improve scanning
- Allow individual sections to have a small Copy action

MOST LIKELY DIAGNOSIS
Present a clearly labelled educational conclusion, for example:
“Most likely diagnosis: Acute coronary syndrome”

Include a confidence label such as “Moderate confidence” and a concise explanation. Do not display certainty or clinical authority language.

CLINICAL REASONING
Present reasoning as several concise learner-facing points, not a hidden chain-of-thought transcript and not a chatbot message.

DIFFERENTIAL DIAGNOSES
Use a comparison layout practical for responsive implementation. Each differential should show:
- Diagnosis name
- Supporting findings
- Opposing or missing findings
- Relative likelihood

Do not use a complex data table if it harms mobile adaptation.

MISSING INFORMATION
Use a clearly visible but neutral section showing what further educational case information would improve reasoning and why it matters.

RED FLAGS
Use restrained red or amber emphasis only for findings explicitly grounded in the case. Do not turn the whole section into an emergency alarm.

PRIMARY NEXT ACTION
At the end of the main analysis content, include a prominent teal button:
“Generate MCQs”

Include the selected MCQ quantity nearby, for example “Generate 5 questions”.

SECONDARY NAVIGATION
A compact sticky section navigator on desktop is acceptable if it remains simple and does not resemble a hospital sidebar. It may list the major analysis sections and highlight the current section.

EDUCATIONAL BOUNDARY
Display a visible disclaimer near the bottom:
“This output is for educational use, may be imperfect and does not replace professional judgment or emergency assessment.”

DO NOT INCLUDE
- Treatment plan
- Medication doses
- Prescriptions
- Patient identity
- Hospital workflow controls
- Chat bubbles
- Editable diagnosis fields
- Clinician sign-off
- Fake AI confidence percentages
- Analytics widgets

Generate one complete desktop screen only.
```

---

# 6. Prompt 3 — Desktop MCQ Practice

Copy the full prompt below into Google Stitch.

```text
Design a polished desktop application screen for CaseLens AI, an AI-powered medical-learning application.

SCREEN: Case-specific MCQ Practice
VIEWPORT: Desktop, approximately 1440px wide
DESIGN DIRECTION: Clinical Workspace

Use the same CaseLens AI visual system as the New Case and Case Analysis screens: light neutral background, white surfaces, deep navy text, restrained teal interactions, subtle borders, moderate rounded corners, minimal shadow, no gradients and no decorative AI graphics.

The screen must feel like focused medical exam practice, not a quiz game, LMS dashboard or generic chatbot.

APPLICATION SHELL
- Compact top navigation with CaseLens AI identity
- Navigation: New Case, Recent Cases, About & Safety
- Keep the active case context visible

PRACTICE HEADER
Show:
- Case title: “Acute central chest pain with autonomic symptoms”
- Progress: “Question 2 of 5”
- A simple progress bar
- Difficulty: Intermediate
- Examination style: NRE

Include a subtle action to return to Case Analysis without losing the current attempt.

QUESTION AREA
Use one primary question panel, not a grid of all questions.

Example stem:
“Which diagnosis best explains this patient’s sudden crushing central chest pain, diaphoresis and radiation to the left arm?”

Show exactly four answer options labelled A, B, C and D.

Use large accessible radio-style option rows with clear hover, selected and focus states.

Before submission:
- Correct answer must not be revealed
- One option may be selected
- Primary button: “Check Answer”

ANSWERED STATE
Design the same screen in a post-answer state where:
- The selected option is visible
- Correctness is clearly shown using icon, label and color together
- The correct answer is identified
- Options become read-only
- A concise explanation is displayed
- The learning objective is displayed
- Optional distractor explanations appear in a restrained secondary area

Example explanation heading:
“Why this is the best answer”

Example learning objective:
“Recognise the typical presentation of acute coronary syndrome.”

NEXT ACTION
After answer reveal, show a prominent teal button:
“Next Question”

For the final question, this action should become:
“View Results”

SIDE CONTENT
A narrow desktop side panel may show:
- Current score so far
- Question navigation indicators
- Case analysis link

Keep it compact. Do not turn it into a course dashboard.

EDUCATIONAL BOUNDARY
Include a subtle note that the score is for self-study and is not an official exam prediction.

DO NOT INCLUDE
- Countdown timer by default
- Leaderboard
- Badges or gamified coins
- Course progress
- Teacher review
- Chat interface
- Patient treatment guidance
- More than four answer options
- Multiple correct answers

Generate one complete desktop screen showing the answered state, while making the unanswered interaction visually understandable.
```

---

# 7. Prompt 4 — Mobile New Case

Copy the full prompt below into Google Stitch after the desktop New Case screen is generated.

```text
Create the mobile adaptation of the approved CaseLens AI New Case desktop screen.

SCREEN: New Case workspace
VIEWPORT: Mobile, approximately 390px wide
DESIGN DIRECTION: Clinical Workspace

Preserve the exact product hierarchy, content, labels, visual identity and safety boundaries from the desktop design. Do not create a separate concept.

Use a compact top app bar with the CaseLens AI identity and a simple navigation menu. Do not use a permanent sidebar.

The mobile screen must include, in this order:
1. Page title: Analyse an educational clinical case
2. Short educational description
3. Educational-use and privacy warning
4. Clinical case textarea
5. Difficulty control
6. Examination style control
7. MCQ count control
8. Primary Analyse Case button
9. Use example case secondary action
10. Local browser-storage note

MOBILE BEHAVIOR
- Stack all controls vertically
- Use full-width fields and buttons
- Keep labels above controls
- Preserve large touch targets
- Keep the primary action easy to reach without using a fixed overlay
- Avoid horizontal scrolling
- Do not collapse the privacy warning into an icon-only element
- Ensure the textarea has sufficient height for meaningful case entry

Use the same light neutral background, white surfaces, deep navy text and restrained teal primary action. No gradients, no chatbot bubbles, no decorative medical imagery and no account controls.

Generate one complete mobile screen only.
```

---

# 8. Prompt 5 — Mobile Case Analysis

Copy the full prompt below into Google Stitch after the desktop analysis screen is generated.

```text
Create the mobile adaptation of the approved CaseLens AI Case Analysis desktop screen.

SCREEN: Case Analysis workspace
VIEWPORT: Mobile, approximately 390px wide
DESIGN DIRECTION: Clinical Workspace

Preserve the same CaseLens AI visual identity, section order, educational language and content hierarchy as the desktop design. Do not turn the mobile design into a chat transcript or a separate simplified product.

MOBILE HEADER
- Compact app bar with CaseLens AI identity
- Clear back or New Case action
- Case title below the app bar
- Compact metadata chips for difficulty and examination style
- Copy and Print actions may use a compact overflow menu if necessary, but labels must remain understandable

ANALYSIS CONTENT
Stack the analysis sections vertically in this exact order:
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

Use readable grouped sections with clear headings. Do not place every line in a separate card. Avoid horizontal tables.

Differential diagnoses should stack as compact comparison groups showing supporting and opposing or missing findings.

The Most Likely Diagnosis section must show calibrated confidence without using a fake numerical percentage.

Show a prominent full-width teal action near the end:
“Generate 5 MCQs”

Keep the educational disclaimer visible and readable.

MOBILE BEHAVIOR
- Single-column flow
- No permanent section sidebar
- An optional compact jump-to-section control may be used
- Preserve comfortable text size and line length
- Do not hide important content behind unexplained icons
- Avoid fixed bottom controls that obscure content

No patient profile, treatment plan, chatbot bubbles, hospital workflow, account controls or analytics.

Generate one complete mobile screen only.
```

---

# 9. Prompt 6 — Mobile MCQ Practice

Copy the full prompt below into Google Stitch after the desktop MCQ screen is generated.

```text
Create the mobile adaptation of the approved CaseLens AI MCQ Practice desktop screen.

SCREEN: Case-specific MCQ Practice
VIEWPORT: Mobile, approximately 390px wide
DESIGN DIRECTION: Clinical Workspace

Preserve the same visual identity and practice behavior as the desktop screen. The mobile version must remain focused, readable and appropriate for exam preparation.

MOBILE HEADER
- Compact CaseLens AI app bar
- Case title shown in shortened readable form
- Progress: Question 2 of 5
- Simple progress bar
- Compact difficulty and examination-style labels

QUESTION FLOW
- Show one question at a time
- Place the question stem above four vertically stacked answer options
- Label options A, B, C and D
- Use full-width accessible option rows with generous touch targets
- Make selection state clear without relying only on color

Design the post-answer state:
- Selected answer remains visible
- Correct or incorrect result is labelled with text and icon
- Correct answer is clearly identified
- Explanation appears immediately below the options
- Learning objective appears in a separate restrained block
- Distractor explanations may be collapsible or secondary

A full-width teal button should appear after the explanation:
“Next Question”

For the final question it becomes:
“View Results”

Include a subtle link to return to Case Analysis without losing progress.

MOBILE BEHAVIOR
- No desktop side panel
- Score-so-far may appear as compact text near progress
- No horizontal option layout
- No tiny controls
- No timer, leaderboard, badges, gamified coins or course dashboard
- Score language must state that it is for self-study and not an official exam prediction

Use the same light neutral background, deep navy text, white content surfaces and restrained teal interactions. No gradients, chatbot bubbles or decorative AI graphics.

Generate one complete mobile screen showing the answered state.
```

---

## 10. Generation Evidence to Preserve

For each generated screen, preserve:

- Stitch project link
- Screen name
- Generation date
- Prompt version used
- Screenshot or export
- Desktop or mobile designation
- Any manual edits made after generation

Recommended evidence names:

```text
P2-D01-desktop-new-case
P2-D02-desktop-case-analysis
P2-D03-desktop-mcq-practice
P2-M01-mobile-new-case
P2-M02-mobile-case-analysis
P2-M03-mobile-mcq-practice
```

---

## 11. Formal Audit Handoff

The formal audit begins only after the six generated screens or a viewable Stitch project link are supplied.

Audit each screen against:

- Approved Phase 1 scope
- Required screen content
- Product hierarchy
- Medical safety language
- Privacy warning
- Accessibility
- Responsive adaptation
- Next.js and Tailwind implementation practicality
- Absence of unsupported features
- Cross-screen visual consistency

Use `docs/phase-2/STITCH-DESIGN-AUDIT.md` as the scoring framework.

The audit output must record each issue as:

```text
Issue ID
Screen
Severity: Blocker | Major | Minor | Observation
Requirement violated
Observed problem
Required correction
Verification result
```

---

## 12. Approval Gate

These prompts do not approve the generated interface automatically.

The initial screen set becomes approved only when:

- All six screens exist
- Blocker issues equal zero
- Major issues are corrected or explicitly accepted
- Desktop and mobile designs use the same system
- P0 workflow remains complete
- Safety and privacy language are visible
- Project owner selects the final reference set
- `SCREEN-REFERENCE-APPROVAL.md` is completed

Until then, Phase 2 remains in progress.
