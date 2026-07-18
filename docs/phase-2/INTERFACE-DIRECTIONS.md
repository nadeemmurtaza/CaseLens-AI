# CaseLens AI

## Interface Directions

### Document Control

**Version:** 1.0  
**Status:** Direction A Recommended  
**Date:** 18 July 2026  
**Phase:** Phase 2

---

## 1. Purpose

This document defines three distinct visual directions for CaseLens AI and recommends one for Google Stitch generation.

Every direction must preserve the approved product scope, routes, interactions, safety boundaries, and responsive behavior. Visual exploration may change presentation, not product truth.

---

## 2. Shared Requirements

All directions must include:

- Application-first New Case screen
- Minimal navigation
- Structured analysis sections
- Clear distinction between facts and interpretation
- Visible uncertainty handling
- Case-specific MCQ practice
- Recent local cases
- About & Safety
- Loading, empty, insufficient-information, and technical-error states
- Desktop and mobile references
- Accessible contrast and interaction targets

All directions must avoid:

- Generic chatbot layouts
- Patient dashboards
- Medical-device styling
- Marketing-homepage dominance
- Purple AI gradients
- Decorative brain imagery
- Fake analytics
- Gamification unrelated to learning

---

# Direction A — Clinical Workspace

## 3. Concept

A calm, modern reasoning workspace that feels precise and trustworthy without implying clinical authority.

The design uses restrained colour, structured surfaces, strong reading hierarchy, and progressive disclosure.

## 3.1 Visual Character

- Calm
- Credible
- Clear
- Efficient
- Contemporary
- Light
- Purposeful

## 3.2 Suggested Palette

| Role | Value |
|---|---|
| Application background | `#F5F7FA` |
| Main surface | `#FFFFFF` |
| Primary text | `#152238` |
| Secondary text | `#5B6678` |
| Border | `#D9E0E8` |
| Primary action | `#0F766E` |
| Primary soft | `#E7F4F2` |
| Information | `#2563EB` |
| Success | `#027A48` |
| Warning | `#B54708` |
| Red flag | `#B42318` |

## 3.3 Typography

- Geist, Inter, or similar application sans-serif
- Medium-weight section headings
- Comfortable body line height
- Compact labels with strong contrast
- No decorative display font

## 3.4 Layout System

- Compact top navigation
- Centred application canvas
- Maximum reading width for long analysis
- Analysis page with optional sticky section index on desktop
- Stacked cards or accordions on mobile
- Subtle borders with limited shadow

## 3.5 Signature Components

- Large case editor card
- Compact segmented controls
- Structured findings cards
- Differential comparison rows
- Restrained confidence label
- Red-flag panel using icon, label, and colour
- Focused MCQ card with one question at a time
- Local-history list with clear metadata

## 3.6 Strengths

- Best reading clarity
- Strongest trust signal
- Easy responsive translation
- Practical to implement in Tailwind
- Supports long AI-generated content
- Distinguishes the app from generic chat products

## 3.7 Risks

- Can become visually generic if spacing and typography are weak
- Can resemble administrative software if cards are overused
- Needs careful warmth to avoid sterile presentation

## 3.8 Mitigation

- Use generous whitespace
- Use restrained soft teal surfaces
- Avoid dense data tables
- Use concise educational microcopy
- Use section rhythm rather than adding decorative graphics

## 3.9 Recommendation

**Recommended as the primary Phase 2 direction.**

It gives the project the best balance of credibility, originality, usability, and implementation feasibility before the deadline.

---

# Direction B — Diagnostic Notebook

## 4. Concept

A more editorial learning environment inspired by a well-organised medical notebook rather than a dashboard.

It uses warm neutral surfaces, stronger typographic hierarchy, annotated sections, and subtle notebook-like structure without literal paper textures or handwriting clichés.

## 4.1 Visual Character

- Thoughtful
- Academic
- Reflective
- Editorial
- Warm
- Study-focused

## 4.2 Suggested Palette

| Role | Value |
|---|---|
| Background | `#F7F4EE` |
| Surface | `#FFFDF8` |
| Primary text | `#1F2937` |
| Secondary text | `#667085` |
| Primary action | `#1D4ED8` |
| Annotation accent | `#C27A18` |
| Soft blue | `#EAF1FF` |
| Warning | `#B45309` |
| Red flag | `#B42318` |

## 4.3 Typography

- Sans-serif application font for controls
- Optional restrained serif only for major page titles or quotations
- Strong editorial spacing between sections

## 4.4 Layout System

- Reading-column emphasis
- Margin notes or section labels on desktop
- Numbered reasoning stages
- Clear chapter-like transitions
- Mobile returns to a single stacked reading flow

## 4.5 Signature Components

- Case “brief” header
- Numbered reasoning sections
- Annotation callouts
- Differential diagnosis comparison notes
- Study-topic bookmark cards
- MCQ explanations resembling structured answer notes

## 4.6 Strengths

- More distinctive than a standard application dashboard
- Strong fit for study and revision
- Encourages deliberate reading
- Gives README screenshots a recognisable visual identity

## 4.7 Risks

- May feel slower or less task-oriented
- Editorial flourishes may complicate mobile layouts
- Serif use can reduce interface consistency
- Warm palette may weaken perceived technical precision

## 4.8 Appropriate Use

Direction B is a viable secondary concept for selected analysis and study-topic details, but should not control the full application shell unless Stitch proves it remains practical and accessible.

---

# Direction C — Focus Mode

## 5. Concept

A concentrated, low-distraction interface optimised for extended case reading and MCQ practice, using darker surfaces and high-contrast content zones.

## 5.1 Visual Character

- Focused
- Serious
- Minimal
- Immersive
- High-contrast

## 5.2 Suggested Palette

| Role | Value |
|---|---|
| Background | `#101828` |
| Surface | `#182230` |
| Raised surface | `#243244` |
| Primary text | `#F2F4F7` |
| Secondary text | `#B8C0CC` |
| Primary action | `#2DD4BF` |
| Information | `#60A5FA` |
| Warning | `#F59E0B` |
| Red flag | `#F97066` |

## 5.3 Typography

- Geist or Inter
- Strong contrast
- Slightly larger body text
- Limited font-weight variation

## 5.4 Layout System

- Minimal chrome
- Strong centre column
- Collapsible section navigation
- Full-width reading mode for analysis
- MCQ practice as an immersive focused panel

## 5.5 Signature Components

- Dark case editor
- Focused loading skeleton
- Compact reasoning navigator
- High-contrast MCQ options
- Distraction-free review mode

## 5.6 Strengths

- Visually memorable
- Strong focus during MCQ practice
- Good for evening study
- Distinct from ordinary educational applications

## 5.7 Risks

- Dark interfaces are harder to execute accessibly
- Red flags and warning colours may become visually aggressive
- Long medical text can feel tiring on dark backgrounds
- Print and PDF output require a separate light presentation
- Evaluators may mistake visual drama for clinical software styling

## 5.8 Appropriate Use

Direction C should be treated as an optional future theme or a focused MCQ sub-mode, not the default MVP direction.

---

## 6. Comparison Matrix

| Criterion | Clinical Workspace | Diagnostic Notebook | Focus Mode |
|---|---:|---:|---:|
| Workflow clarity | 5/5 | 4/5 | 4/5 |
| Reading comfort | 5/5 | 5/5 | 3/5 |
| Mobile adaptability | 5/5 | 4/5 | 4/5 |
| Accessibility simplicity | 5/5 | 4/5 | 3/5 |
| Implementation feasibility | 5/5 | 4/5 | 3/5 |
| Visual distinctiveness | 4/5 | 5/5 | 5/5 |
| Medical-learning fit | 5/5 | 5/5 | 4/5 |
| Deadline suitability | 5/5 | 4/5 | 3/5 |

---

## 7. Selected Direction

**Selected for initial Stitch generation:** Direction A — Clinical Workspace

### Rationale

Direction A:

- Best supports the approved user flow
- Handles long structured AI output
- Is easiest to implement reliably in Next.js and Tailwind
- Adapts cleanly to mobile
- Supports accessible status states
- Avoids chatbot and hospital-dashboard clichés
- Provides a professional project presentation without excessive visual risk

### Permitted Influence From Direction B

The selected direction may borrow:

- Strong editorial section rhythm
- Numbered reasoning stages
- Study-topic bookmark treatment
- More generous reading spacing

It must not introduce a mixed visual system or decorative notebook imitation.

---

## 8. Stitch Generation Strategy

Generate in this order:

1. Clinical Workspace New Case desktop
2. Clinical Workspace Analysis desktop
3. Clinical Workspace MCQ desktop
4. Matching mobile screens
5. Remaining states and supporting views
6. One controlled Diagnostic Notebook alternative for the Analysis screen only

Do not generate every screen in all three directions. That would consume time while multiplying inconsistency, a traditional design-process achievement best avoided here.

---

## 9. Approval State

**Direction A recommendation:** Approved for initial generation  
**Final visual approval:** Pending Stitch output and audit  
**Implementation authorization:** Not yet granted
