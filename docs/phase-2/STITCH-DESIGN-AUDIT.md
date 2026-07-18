# CaseLens AI

## Google Stitch Design Audit

### Document Control

**Version:** 1.0  
**Status:** Ready for Use  
**Date:** 18 July 2026  
**Phase:** Phase 2

---

## 1. Purpose

This document defines how Google Stitch outputs will be reviewed before any screen is accepted as an implementation reference.

A polished image is not proof of a valid product design. Each screen must be checked against the approved application behavior, safety boundaries, accessibility requirements, responsive needs, and implementation constraints.

---

## 2. Audit Inputs

The audit uses:

- `docs/PROJECT-CHARTER.md`
- `docs/PRODUCT-REQUIREMENTS.md`
- `docs/USER-FLOWS-AND-INFORMATION-ARCHITECTURE.md`
- `docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md`
- `docs/PHASE-1-BASELINE-APPROVAL.md`
- `docs/phase-2/STITCH-DESIGN-BRIEF.md`
- `docs/phase-2/INTERFACE-DIRECTIONS.md`
- Stitch desktop and mobile outputs

---

## 3. Finding Severity

| Severity | Meaning | Approval effect |
|---|---|---|
| Blocker | Breaks a P0 flow, safety boundary, or core responsive behavior | Screen set rejected |
| Major | Significant usability, accessibility, or consistency failure | Must be corrected |
| Minor | Localised issue with limited impact | May be corrected before implementation |
| Observation | Improvement opportunity without current failure | Record for implementation |

---

## 4. Audit Method

For each screen:

1. Identify the approved route or state represented.
2. Confirm required content and actions.
3. Trace entry and exit actions.
4. Check P0 behavior.
5. Check safety and privacy messaging.
6. Check hierarchy and readability.
7. Check mobile behavior.
8. Check accessibility.
9. Check consistency with the selected direction.
10. Check whether the design is practical to build.
11. Record findings with severity and corrective action.

Do not approve a collection merely because individual screens look related. The full user journey must remain coherent.

---

## 5. Scope Compliance Checklist

- [ ] Product is presented as an application, not a promotional website
- [ ] No login, account, profile, or subscription dependency
- [ ] No patient-record workflow
- [ ] No diagnosis or treatment claim
- [ ] No course-management or LMS features
- [ ] No medical-image upload
- [ ] No fake analytics or fabricated metrics
- [ ] No generic chatbot transcript
- [ ] No unsupported navigation item
- [ ] No official exam-body affiliation claim

Any unsupported feature must be removed before approval.

---

## 6. Navigation Audit

- [ ] New Case is directly accessible
- [ ] Recent Cases is accessible
- [ ] About & Safety is accessible
- [ ] Navigation labels are consistent on desktop and mobile
- [ ] Current location is understandable
- [ ] No administrative sidebar is introduced
- [ ] Back and return actions are clear
- [ ] Case Analysis remains connected to MCQ Practice
- [ ] MCQ Practice remains connected to the source case
- [ ] Invalid or missing local cases have a recovery path

---

## 7. New Case Workspace Audit

- [ ] Case editor is the primary visual element
- [ ] Educational-use notice is visible
- [ ] No-patient-data warning is visible
- [ ] Input has a persistent label
- [ ] Difficulty selector exists
- [ ] Examination-style selector exists
- [ ] MCQ-count selector exists
- [ ] Analyse Case is the clear primary action
- [ ] Duplicate submission is visually preventable
- [ ] Empty-input error location is clear
- [ ] Provider-error recovery preserves the case input
- [ ] Mobile controls stack without horizontal overflow

---

## 8. Loading and Error Audit

- [ ] Loading state communicates active processing
- [ ] Loading does not show a fabricated percentage
- [ ] Duplicate submission is disabled
- [ ] Skeletons match the expected result structure
- [ ] Technical failures use plain language
- [ ] Error messages do not resemble clinical alarms
- [ ] Retry is offered only where appropriate
- [ ] User input remains recoverable
- [ ] No secret, stack trace, or provider internals are exposed
- [ ] Local-storage failure is non-blocking

---

## 9. Analysis Workspace Audit

- [ ] Case Summary exists
- [ ] Supplied Facts exist
- [ ] Positive Findings exist
- [ ] Negative Findings exist when applicable
- [ ] Most Likely Diagnosis supports a null state
- [ ] Confidence is expressed without a false certainty gauge
- [ ] Clinical Reasoning is readable as learner-facing points
- [ ] Differential Diagnoses support comparison
- [ ] Missing Information is prominent
- [ ] Red Flags are visually distinct but restrained
- [ ] Study Topics are visible
- [ ] Educational Disclaimer is visible
- [ ] Individual section copy controls are understandable
- [ ] Copy All exists
- [ ] Print / Save PDF exists
- [ ] Generate MCQs is the clear next action
- [ ] New Case remains available

---

## 10. Insufficient-Information Audit

- [ ] State is presented as a valid analytical outcome, not a technical crash
- [ ] Heading explains that more information is needed
- [ ] Supplied facts remain visible
- [ ] Missing information is prominent
- [ ] Unsupported certainty is absent
- [ ] Low-confidence possibilities are clearly qualified
- [ ] Edit Case action exists
- [ ] Start New Case action exists
- [ ] MCQ availability matches the approved behavior

---

## 11. MCQ Practice Audit

- [ ] Case context remains identifiable
- [ ] Question progress is clear
- [ ] Question stem is readable
- [ ] Exactly four options are represented
- [ ] One option can be selected
- [ ] Correct answer is hidden before submission
- [ ] Check Answer is clear
- [ ] Correctness uses text or icon plus colour
- [ ] Explanation is readable
- [ ] Learning objective is visible
- [ ] Next Question is clear
- [ ] Selection is locked after checking
- [ ] Mobile option targets are large enough
- [ ] No exam-ranking or prediction claim appears

---

## 12. MCQ Completion Audit

- [ ] Correct count is visible
- [ ] Total count is visible
- [ ] Percentage is visible
- [ ] Score is described as self-study feedback
- [ ] Review Questions action exists
- [ ] Return to Case Analysis exists
- [ ] Start New Case exists
- [ ] No streaks, badges, ranking, or mastery claims are invented

---

## 13. Recent Cases Audit

- [ ] Local-only storage notice is visible
- [ ] Safe generated title is shown
- [ ] Date and time are shown
- [ ] Examination style is shown
- [ ] Analysis status is shown
- [ ] MCQ status is shown
- [ ] Reopen exists
- [ ] Delete one exists
- [ ] Clear all exists with stronger confirmation
- [ ] Empty state exists
- [ ] Empty state offers Start a New Case
- [ ] No account-sync implication appears

---

## 14. About & Safety Audit

- [ ] Product purpose is explained
- [ ] Target user is explained
- [ ] AI use is explained
- [ ] Educational limitation is clear
- [ ] No-patient-data rule is clear
- [ ] Local-storage model is clear
- [ ] Known limitations are clear
- [ ] Professional and emergency-evaluation boundary is clear
- [ ] Content is readable rather than hidden in legalistic density

---

## 15. Visual-System Audit

- [ ] Selected Clinical Workspace direction is recognisable
- [ ] Colour tokens are used consistently
- [ ] Primary actions use one consistent treatment
- [ ] Warning and danger states are not overused
- [ ] Typography hierarchy is consistent
- [ ] Card radius and border treatment are consistent
- [ ] Spacing follows a coherent rhythm
- [ ] Icons share one style
- [ ] Shadows are restrained
- [ ] No purple AI gradient or glowing orb appears
- [ ] No decorative medical cliché appears

---

## 16. Accessibility Audit

- [ ] Text contrast appears capable of meeting WCAG AA
- [ ] Focus states are specified or visually supported
- [ ] Form labels are not replaced by placeholders
- [ ] Errors can be associated with fields
- [ ] Status does not depend on colour alone
- [ ] Heading order is logical
- [ ] Touch targets are at least 44 by 44 px
- [ ] Text remains readable at mobile width
- [ ] Motion is not required to understand state
- [ ] Content order supports screen readers

A static design cannot prove implementation accessibility, but it must not make accessible implementation needlessly difficult.

---

## 17. Responsive Audit

- [ ] Desktop reference exists
- [ ] Mobile reference exists
- [ ] Mobile is intentionally composed
- [ ] No horizontal scrolling is required
- [ ] Actions remain visible and reachable
- [ ] Analysis sections preserve logical order
- [ ] Section navigation adapts appropriately
- [ ] MCQ options remain readable
- [ ] Dialogs and confirmations fit mobile
- [ ] Navigation remains consistent

---

## 18. Implementation-Practicality Audit

- [ ] Layout can be built with standard Next.js and Tailwind patterns
- [ ] Components are reusable
- [ ] Generated content lengths can expand safely
- [ ] Empty arrays and null diagnosis states are supported
- [ ] Long case titles do not break layout
- [ ] Long option text wraps correctly
- [ ] Print view can be derived
- [ ] No essential interaction depends on an unexplained animation
- [ ] No custom illustration is required for the core workflow
- [ ] Design can be implemented within the project deadline

---

## 19. Originality Audit

- [ ] Interface is not merely a chat box with response bubbles
- [ ] Structured reasoning is visually central
- [ ] Facts, inference, and uncertainty are differentiated
- [ ] MCQs remain linked to the case
- [ ] Local revision history is visible
- [ ] Visual identity is recognisable in screenshots
- [ ] Distinctiveness does not come from unsupported features

---

## 20. Audit Finding Template

```text
Finding ID:
Screen:
Severity:
Requirement:
Observed issue:
Why it matters:
Required correction:
Status:
Evidence after correction:
```

---

## 21. Approval Rule

A Stitch reference set may be approved only when:

- No Blocker findings remain
- No unresolved Major findings remain
- All required desktop and mobile screens exist
- P0 flows are visually complete
- Safety and privacy boundaries are represented
- The selected visual system is consistent
- The screen set is practical to implement
- The project owner records approval

---

## 22. Current Audit Status

**Stitch outputs received:** No  
**Audit started:** Framework prepared  
**Blocking findings:** Not yet assessed  
**Approval:** Pending
