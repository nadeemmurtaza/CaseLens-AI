# CaseLens AI

## Final Course Project Charter

### Document Control

**Project Name:** CaseLens AI  
**Project Type:** AI-Powered Web Application  
**Course:** ACT AI Final Course Project  
**Status:** Approved Baseline  
**Version:** 1.0  
**Date:** 18 July 2026  
**Submission Deadline:** Monday, 27 July 2026, 11:59 PM PKT  
**Submission Method:** Public GitHub repository link only  
**Deployment Target:** Vercel  
**AI Provider:** Gemini API

---

## 1. Project Definition

CaseLens AI is an interactive medical-learning application that helps students practise structured clinical reasoning.

A learner enters an educational clinical case. The application analyses the supplied information, identifies important findings, explains diagnostic reasoning, presents reasonable differential diagnoses, highlights missing information and generates case-specific MCQs.

CaseLens AI is an application because users actively:

- Enter information
- Submit cases
- Receive generated results
- Interact with structured analysis
- Generate MCQs
- Review answers
- Save recent cases locally
- Copy or print learning material

It is not a static informational website.

---

## 2. Assignment Requirements

The project must satisfy all of the following course requirements:

### AR-01: Original Idea

The application must use an original concept rather than copying an existing application or template.

### AR-02: Real Problem

The application must solve a clearly defined real-world problem.

### AR-03: Complete Working Application

The application must function from input through final output.

### AR-04: AI-Powered Feature

The application must contain a working AI feature.

### AR-05: Public GitHub Repository

The complete source code must be available in a public GitHub repository.

### AR-06: Public Deployment

The application must be deployed live and accessible through a public URL.

### AR-07: Comprehensive README

The repository README must serve as the complete project report.

### AR-08: Submission Format

Only the public GitHub repository link will be submitted through the portal.

### AR-09: Deadline

The project must be submitted by:

> Monday, 27 July 2026 at 11:59 PM PKT

---

## 3. Evaluation Criteria

The project will be marked on:

1. Idea
2. Completion
3. Deployment
4. Reporting through the README

Every development decision must strengthen at least one of these four areas.

Features that do not improve originality, completion, deployment quality or reporting should not be added to the MVP.

---

## 4. Problem Statement

Medical students frequently struggle to analyse clinical cases systematically.

Common problems include:

- Jumping directly to a diagnosis
- Missing important clinical clues
- Ignoring relevant negative findings
- Confusing supplied facts with assumptions
- Producing poorly structured differential diagnoses
- Memorising answers without understanding the reasoning
- Failing to identify missing information
- Finding it difficult to convert one case into useful revision material
- Using general AI chatbots that return unstructured or overly confident answers

CaseLens AI solves this problem by providing a controlled clinical-reasoning workflow.

---

## 5. Proposed Solution

CaseLens AI will transform a clinical case into a structured educational analysis.

The application workflow will be:

```text
Enter an educational clinical case
        ↓
Validate the case input
        ↓
Send the case securely to Gemini
        ↓
Receive structured clinical analysis
        ↓
Display facts, reasoning and uncertainty separately
        ↓
Generate case-specific MCQs
        ↓
Review answers and explanations
        ↓
Copy, print or revisit the case
```

The application will guide the learner through reasoning rather than merely returning a diagnosis.

---

## 6. Target Users

The primary users are:

- MBBS students
- NRE candidates
- USMLE candidates
- PLAB candidates
- MRCP candidates
- Medical learners practising case-based questions

The application assumes that users have basic medical knowledge.

---

## 7. Core User Outcome

After analysing a case, the learner should understand:

1. What information was explicitly supplied
2. Which findings are important
3. Which negative findings matter
4. What the leading diagnosis may be
5. Why that diagnosis is being considered
6. Which alternatives remain possible
7. What information is missing
8. Whether the case contains important red flags
9. Which topics should be revised
10. How the case could appear in examination-style questions

---

## 8. Originality Position

CaseLens AI is not a medical chatbot with a renamed text box.

Its originality comes from combining:

- Structured case extraction
- Separation of facts and inference
- Positive and negative finding analysis
- Calibrated diagnostic reasoning
- Differential diagnosis comparison
- Missing-information detection
- Red-flag identification
- Case-specific study recommendations
- Case-specific MCQ generation
- Local revision history

The complete reasoning workflow is the product.

Gemini is the reasoning engine inside that workflow, not the product by itself.

---

## 9. Difference From a General Chatbot

A general chatbot:

- Accepts unrestricted conversation
- Produces unpredictable response structures
- May drift outside the original task
- May mix facts and assumptions
- May provide excessive certainty
- Does not enforce a learning sequence

CaseLens AI will:

- Accept a defined type of input
- Enforce a structured output
- Separate supplied facts from inference
- Handle insufficient information explicitly
- Apply visible medical-safety boundaries
- Generate case-related learning material
- Present results through a purpose-built interface

---

## 10. Difference From an LMS

CaseLens AI is not a learning-management system.

It will not manage:

- Courses
- Teachers
- Student enrollment
- Attendance
- Assignments
- Certificates
- Institutional reporting
- Class schedules
- Fee collection

It is a focused clinical-reasoning application.

---

## 11. Minimum Viable Product

The MVP will include the following features.

### 11.1 Application Landing Screen

The opening screen must explain:

- What CaseLens AI does
- Who it is intended for
- How to begin
- That it is for education only
- That users must not enter identifiable patient information

The landing screen must lead directly into the application workflow.

It must not become a long marketing homepage.

### 11.2 Clinical Case Input

The user must be able to:

- Type a clinical case
- Paste a clinical case
- Edit the case
- Clear the input
- Submit the case
- View input guidance

The application must reject:

- Empty input
- Meaningless input
- Clearly non-medical input
- Input that is too short for useful analysis

### 11.3 Analysis Configuration

The user may select:

#### Difficulty

- Basic
- Intermediate
- Advanced

#### Examination Style

- General Medical
- NRE
- USMLE
- PLAB
- MRCP

#### MCQ Quantity

- 3
- 5
- 10

These options must not claim official affiliation with an examination body.

### 11.4 AI Case Analysis

The application must produce the following sections:

#### Case Summary

A brief summary of the submitted case.

#### Supplied Facts

Only information explicitly present in the user’s input.

#### Important Positive Findings

Findings that support one or more possible diagnoses.

#### Important Negative Findings

Absent or denied findings that influence interpretation.

#### Most Likely Diagnosis

The leading educational interpretation when sufficient information exists.

#### Clinical Reasoning

A clear explanation connecting the findings to the leading interpretation.

#### Differential Diagnoses

Reasonable alternatives with supporting and opposing findings.

#### Missing Information

Additional history, examination or investigation information that would improve the interpretation.

#### Red Flags

Urgent or high-risk findings identified in the supplied case.

#### Recommended Study Topics

Topics the learner should revise based on the case.

#### Educational Disclaimer

A visible statement that the output is for learning and does not replace professional medical judgment.

### 11.5 Insufficient Information Handling

When the case does not contain enough information, the application must:

- Say that the information is insufficient
- Avoid declaring a confirmed diagnosis
- Explain what can be inferred
- Explain what cannot be inferred
- Identify the missing information
- Avoid inventing examination findings
- Avoid inventing laboratory results
- Avoid inventing imaging results
- Avoid inventing patient history

### 11.6 MCQ Generator

The user must be able to generate MCQs based on the analysed case.

Each MCQ must include:

- Question stem
- Answer options
- Correct answer
- Explanation
- Learning objective

MCQs should test understanding and reasoning rather than merely asking the user to repeat the diagnosis.

### 11.7 Recent Cases

The application will store a limited recent-case history in the user’s browser.

The user must be able to:

- View recent cases
- Reopen a case
- Delete one case
- Clear all recent cases

The interface must explain that these cases are stored locally on the device.

No cloud medical-history system will be built.

### 11.8 Copy Function

The user must be able to copy:

- Full case analysis
- Individual analysis sections
- Generated MCQs

### 11.9 Print Function

The user must be able to print or save as PDF:

- Case analysis
- Generated MCQs

The print view must exclude unnecessary navigation and buttons.

### 11.10 Error Handling

The application must provide useful messages for:

- Empty input
- Invalid input
- API timeout
- Gemini service failure
- Invalid AI response
- Network failure
- Repeated submission
- Local-storage failure

The application must not show success when the request actually failed.

### 11.11 Responsive Application

The primary workflow must work on:

- Mobile
- Tablet
- Laptop
- Desktop

Mobile users must be able to:

- Enter a case
- Submit it
- Read the analysis
- Generate MCQs
- Review answers
- Copy content
- Open recent cases

---

## 12. Application Screens

The MVP should contain the following application screens or views.

### Screen 1: Welcome and Case Entry

Contains:

- Application identity
- Short explanation
- Safety notice
- Case input
- Configuration controls
- Analyse Case action

### Screen 2: Analysis Loading State

Contains:

- Clear processing status
- Cancel or return behaviour where practical
- No fake progress percentage
- No unnecessary waiting animation

### Screen 3: Case Analysis

Contains:

- Submitted case reference
- Structured analysis sections
- Copy controls
- Print control
- Generate MCQs action
- New Case action

### Screen 4: MCQ Practice

Contains:

- One MCQ at a time or clearly separated MCQs
- Answer selection
- Answer reveal
- Explanation
- Progress
- Final result summary

### Screen 5: Recent Cases

Contains:

- Saved local cases
- Reopen action
- Delete action
- Clear-all action
- Local-storage explanation

### Screen 6: About and Safety

Contains:

- Educational purpose
- Limitations
- Privacy guidance
- AI-use explanation
- No-patient-data rule

These may be separate routes or application panels, depending on the final interface design.

---

## 13. AI Provider

Gemini API will power the live AI feature.

Gemini will be used for:

- Structured case analysis
- Clinical-reasoning explanation
- Differential diagnosis generation
- Missing-information identification
- Red-flag identification
- Study-topic generation
- MCQ generation

The Gemini API key must remain server-side.

It must not be exposed in:

- Frontend code
- Public repository history
- Screenshots
- README
- Browser responses
- Client-side environment variables

---

## 14. Medical Safety Boundaries

CaseLens AI is an educational application.

It must not:

- Diagnose a real patient
- Prescribe medication
- Recommend individualized treatment
- Replace emergency evaluation
- Claim clinical confirmation without evidence
- Provide medical clearance
- Store real patient records
- Encourage users to ignore qualified clinicians
- Present generated information as guaranteed correct

Users must be told not to enter:

- Patient names
- CNIC numbers
- Passport numbers
- Addresses
- Phone numbers
- Email addresses
- Hospital record numbers
- Any other identifiable patient information

---

## 15. Privacy Model

The MVP will use:

- Temporary server-side processing for Gemini requests
- Browser localStorage for recent cases
- No user accounts
- No cloud clinical-case database
- No analytics containing raw medical case text

The application must not intentionally retain submitted case content on the server after the request is completed.

Server logging must not record complete case text.

---

## 16. Technical Baseline

### Application Framework

- Next.js
- TypeScript
- Tailwind CSS

### AI

- Gemini API
- Server-side API route
- Structured JSON response
- Schema validation

### Storage

- Browser localStorage

### Source Control

- GitHub
- Public repository
- Meaningful commit history

### Deployment

- Vercel
- Public URL
- Secure environment variables

### Design

- Google Stitch for screen exploration
- Final interface implemented in application code

### Evidence and Review

- NotebookLM private evidence workspace

---

## 17. Repository Requirements

The public GitHub repository must contain:

- Complete source code
- README
- Licence or usage notice where appropriate
- `.gitignore`
- `.env.example`
- Installation instructions
- Development instructions
- Build instructions
- Testing instructions
- Architecture explanation
- AI feature explanation
- Screenshots
- Live deployment link
- Known limitations
- Safety statement

The repository must not contain:

- API keys
- `.env.local`
- Passwords
- Private credentials
- Real patient information
- Generated secrets

---

## 18. Deployment Requirements

The application must:

- Be deployed on Vercel
- Have a public URL
- Load without authentication
- Complete the real Gemini workflow
- Work after a fresh deployment
- Use production environment variables
- Display useful errors
- Remain usable on mobile
- Link back to the public repository where appropriate

The live URL must be tested before submission.

A successful local run does not prove deployment.

---

## 19. README Requirements

The README must serve as the complete project report.

It must include:

1. Project title
2. Project overview
3. Problem statement
4. Proposed solution
5. Originality explanation
6. Target users
7. Core features
8. AI-powered feature
9. Application workflow
10. Screenshots
11. Technology stack
12. Architecture
13. Installation instructions
14. Environment-variable setup
15. Local-development instructions
16. Testing instructions
17. Deployment instructions
18. Public live URL
19. Safety and privacy boundaries
20. Known limitations
21. Future improvements
22. Author information
23. Credits and acknowledgements where applicable

The README must make the project understandable without requiring the evaluator to inspect every source file.

---

## 20. Grading Alignment

### 20.1 Idea

Evidence must demonstrate:

- A clearly defined medical-learning problem
- An original structured reasoning workflow
- Distinction from chatbots and LMS platforms
- Appropriate use of AI
- Focused target users

### 20.2 Completion

Evidence must demonstrate:

- Functional case input
- Working Gemini analysis
- Structured output
- Working MCQ generation
- Error handling
- Responsive design
- Local history
- Copy and print functionality
- No known submission-blocking issue

### 20.3 Deployment

Evidence must demonstrate:

- Public Vercel URL
- Successful production build
- Working production AI requests
- Correct environment-variable configuration
- Mobile production verification

### 20.4 Reporting

Evidence must demonstrate:

- Comprehensive README
- Screenshots
- Setup instructions
- Feature explanations
- AI explanation
- Testing evidence
- Deployment documentation
- Safety and limitations

---

## 21. Out of Scope

The following will not be included in the MVP:

- Native Android application
- Native iOS application
- App-store publication
- Authentication
- User accounts
- Subscription payments
- Course management
- Instructor dashboard
- Institutional administration
- Attendance
- Certificates
- Social features
- Cloud case history
- Real patient records
- Patient diagnosis
- Treatment planning
- Prescription generation
- Medical-image analysis
- Voice consultation
- Hospital integration
- Electronic medical records
- Multiple AI providers
- Fine-tuned models
- Advanced analytics
- Team collaboration
- Public case sharing

---

## 22. Completion Definition

The project may be called complete only when:

- The approved MVP is implemented
- The Gemini feature works
- Required error states work
- Mobile and desktop workflows work
- Tests pass against the latest code
- The public GitHub repository is current
- The Vercel deployment works
- The README is complete
- No API key is exposed
- No known submission-blocking issue remains
- The final repository link is ready for portal submission

---

## 23. Required Final Evidence

The project evidence set must include:

- Approved Project Charter
- Product Requirements Document
- Assignment Traceability Matrix
- User-flow specification
- AI system-prompt specification
- Stitch design brief
- Selected interface designs
- Technical architecture
- Testing matrix
- Test results
- Final screenshots
- Public GitHub repository
- Final commit
- Public Vercel URL
- Final README
- README audit
- Final submission audit

---

## 24. Current Project Status

**Assignment requirements:** Defined  
**Project concept:** Defined  
**Project type:** AI-powered web application  
**MVP scope:** Defined  
**AI provider:** Gemini API  
**Repository:** Created  
**Application development:** Not started  
**Deployment:** Not started  
**README:** Not started  
**Current Phase:** Phase 1 — Requirements and Product Definition

---

## 25. Next Document

The next controlled project document is:

> **CaseLens AI Product Requirements Document**

It will define exact functional behaviour, application states, field rules, AI response contracts, screen requirements and feature acceptance criteria.
