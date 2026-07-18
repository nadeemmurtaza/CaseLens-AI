# CaseLens AI

## Phase 2 — Verified Design Preparation and Interface Direction

### Document Control

**Version:** 1.0  
**Status:** In Progress  
**Date:** 18 July 2026  
**Approved Phase 1 baseline:** `9bd8eb950cef9d991b9a41e1078e8149c1a0128a`  
**Branch:** `agent/phase-2-design-preparation`

---

## 1. Objective

Phase 2 converts the approved product requirements into a coherent, testable visual and interaction direction for CaseLens AI.

The phase must establish:

- A verified input brief for Google Stitch
- A small set of distinct interface directions
- A recommended direction grounded in product requirements
- Complete desktop and mobile screen references
- A design-audit method
- A formal approval record for the selected screen set

Phase 2 does not authorize feature expansion.

---

## 2. Approved Design Target

CaseLens AI is a focused medical-learning application for structured clinical reasoning.

The interface must help a learner:

1. Enter an educational clinical case
2. Configure difficulty, examination style, and MCQ count
3. Submit the case safely
4. Review structured analysis
5. Generate and attempt MCQs
6. Revisit locally saved cases
7. Understand privacy and educational limitations

The product must feel like one coherent reasoning workspace.

It must not resemble:

- A marketing website
- A hospital-management system
- An electronic patient record
- A generic chatbot
- A learning-management system
- A medical-device interface
- A dashboard full of fabricated analytics

---

## 3. Source Documents

Phase 2 is governed by:

- `docs/PROJECT-CHARTER.md`
- `docs/PRODUCT-REQUIREMENTS.md`
- `docs/USER-FLOWS-AND-INFORMATION-ARCHITECTURE.md`
- `docs/AI-FEATURE-AND-PROMPT-SPECIFICATION.md`
- `docs/ASSIGNMENT-TRACEABILITY-MATRIX.md`
- `docs/PHASE-1-BASELINE-APPROVAL.md`

Where visual preferences conflict with product behavior, the approved product behavior wins.

---

## 4. Phase 2 Deliverables

| # | Deliverable | Repository path | Status |
|---|---|---|---|
| 1 | Phase 2 Plan | `docs/phase-2/PHASE-2-PLAN.md` | Created |
| 2 | Verified Stitch Design Brief | `docs/phase-2/STITCH-DESIGN-BRIEF.md` | Planned |
| 3 | Interface Directions | `docs/phase-2/INTERFACE-DIRECTIONS.md` | Planned |
| 4 | Stitch Design Audit | `docs/phase-2/STITCH-DESIGN-AUDIT.md` | Planned |
| 5 | Screen Reference Approval | `docs/phase-2/SCREEN-REFERENCE-APPROVAL.md` | Planned |
| 6 | Stitch-generated screen references | External Stitch project plus exported evidence | Pending generation |
| 7 | Final selected reference set | Repository screenshots or documented links | Pending approval |

---

## 5. Required Screen Set

The minimum design reference set contains:

1. New Case workspace
2. Analysis loading state
3. Validation or provider-error state
4. Case Analysis workspace
5. MCQ Practice workspace
6. MCQ completion and score state
7. Recent Cases view
8. Recent Cases empty state
9. About & Safety view
10. Mobile equivalents for the principal journey

A design set that shows only polished success screens is incomplete.

---

## 6. Design Principles

### DP-01 — Application First

The first screen must allow the learner to begin a case without traversing a promotional homepage.

### DP-02 — Calm Clinical Credibility

The interface should feel precise, calm, readable, and educational without implying that it is a clinical-care system.

### DP-03 — Reasoning Before Decoration

Visual hierarchy must help learners distinguish:

- Supplied facts
- Findings
- Interpretation
- Uncertainty
- Differential diagnoses
- Missing information
- Red flags
- Study topics

### DP-04 — Progressive Disclosure

Long outputs must use sections, cards, accordions, tabs, or anchored navigation where appropriate. The page must not become an uninterrupted wall of generated text.

### DP-05 — Safety Is Visible but Proportionate

Educational and privacy boundaries must be visible at relevant moments without dominating every screen.

### DP-06 — Mobile Is a Primary Layout

Mobile references must preserve task order, reading hierarchy, actions, and error recovery. They must not be desktop layouts crushed into a narrower rectangle.

### DP-07 — No Fake Intelligence Theatre

Avoid decorative brain graphics, glowing AI orbs, fake diagnostic certainty meters, fabricated patient charts, and meaningless analytics.

### DP-08 — Accessible by Default

Designs must support readable text sizes, keyboard focus, clear labels, sufficient contrast, non-colour status cues, and touch targets of at least 44 by 44 pixels.

---

## 7. Recommended Visual Direction

The recommended starting direction is **Clinical Workspace**.

It uses:

- Light neutral backgrounds
- White or subtly tinted work surfaces
- Deep navy text
- Restrained teal as the primary action colour
- Amber and red only for caution and red-flag states
- Generous whitespace
- Compact but readable controls
- Structured cards and section navigation
- Minimal illustration

The direction is selected because it best supports trust, readability, mobile adaptation, and the application-first workflow.

Alternative directions remain documented for comparison but should not dilute the final product into a visual compromise committee.

---

## 8. Phase Workflow

```text
Verify approved flows
→ Prepare Stitch brief
→ Generate three design directions
→ Select a primary direction
→ Generate full desktop screen set
→ Generate mobile equivalents
→ Audit against requirements
→ Correct failures
→ Record approved reference set
→ Authorize implementation
```

---

## 9. Audit Categories

Every generated design must be reviewed for:

- Scope compliance
- Screen completeness
- Navigation correctness
- User-flow continuity
- Content hierarchy
- Loading and error states
- Medical-safety presentation
- Privacy messaging
- Accessibility
- Responsive behavior
- Implementation practicality
- Originality
- Visual consistency

A visually attractive design that fails the workflow is rejected.

---

## 10. Phase 2 Completion Gate

Phase 2 is complete only when:

- The Stitch design brief is approved
- At least three interface directions are documented
- One direction is selected
- Required desktop screens exist
- Required mobile screens exist
- Loading, empty, and error states exist
- The design audit is completed
- Blocking audit findings are resolved
- The final screen reference set is recorded
- The project owner approves the selected direction
- The Phase 2 documentation is merged into `main`

---

## 11. Current Status

**Phase 1:** Complete and approved  
**Phase 2:** Started  
**Current activity:** Verified design preparation  
**UI implementation:** Not started  
**Stitch generation:** Not started  
**Phase 2 approval:** Pending
