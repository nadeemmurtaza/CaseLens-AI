# CaseLens AI

## NotebookLM Research and Evidence Plan

### Document Control

**Project:** CaseLens AI  
**Document:** NotebookLM Research and Evidence Plan  
**Version:** 1.0  
**Status:** Proposed for Approval  
**Date:** 18 July 2026  
**Notebook Visibility:** Private  
**Notebook Name:** CaseLens AI — Final Project Evidence Hub  

---

## 1. Purpose

NotebookLM will serve as the project's source-grounded research, requirement-audit, evidence-organization, documentation-review, and presentation-preparation workspace.

NotebookLM is not:

- The application builder
- The production AI feature
- A replacement for testing
- A source of execution evidence
- A place to store credentials or real patient information

The live AI feature inside CaseLens AI remains the Gemini API. NotebookLM supports the project around the application rather than appearing inside it.

---

## 2. Workspace Rule

Create one private notebook named:

> **CaseLens AI — Final Project Evidence Hub**

Keep the approved project evidence in this notebook so requirement comparisons use one controlled source collection.

Do not divide Phase 1 evidence across separate notebooks unless a later platform limitation makes that necessary and the split is documented.

---

## 3. Privacy and Security Rules

Never upload:

- Gemini API keys
- `.env` files containing real values
- Passwords
- GitHub personal access tokens
- Vercel credentials
- Private account recovery information
- Real patient details
- Identifiable clinical cases
- Private medical records
- Raw production logs containing sensitive content
- Proprietary credentials or secrets

Only fictional, de-identified, or clearly educational case material may be used.

NotebookLM output remains informational and must not be treated as medical advice, software execution proof, or automatic approval.

---

## 4. Source Register

Upload the following sources as they become available.

### Phase 1 Sources

1. Assignment Requirements Source Record
2. Official announcement and marking criteria
3. Full portal assignment brief, when obtained
4. Project Charter
5. Product Requirements Document
6. Assignment Traceability Matrix
7. User Flows and Information Architecture
8. AI Feature and Prompt Specification
9. Risks, Assumptions and Decisions Register
10. Phase 1 Baseline Approval Record

### Design Sources

11. Verified Stitch Input Brief
12. Selected Stitch screenshots
13. Design audit findings
14. Final approved screen references

### Architecture and Development Sources

15. Technical Architecture Document
16. Repository structure record
17. Environment and secret-management plan
18. Relevant Gemini API documentation used during implementation
19. Architecture decisions

### Testing Sources

20. Testing and Acceptance Criteria
21. Formal Testing Matrix
22. Unit and integration test results
23. End-to-end test results
24. Accessibility test results
25. Mobile and desktop verification records
26. Prompt-quality and safety test results
27. Secret-scan results
28. Known-issues register

### Release and Reporting Sources

29. Deployment checklist
30. Vercel production verification record
31. Final screenshots
32. README draft
33. Final README
34. README Gap Report
35. Final Evidence-Based Submission Audit
36. Submission record

---

## 5. Source Naming Standard

Use filenames that identify project, phase, document, and version.

Recommended pattern:

```text
CaseLens-AI_Phase-1_Project-Charter_v1.0
CaseLens-AI_Testing_Formal-Matrix_v1.0
CaseLens-AI_Final-README_v1.0
```

When a source changes materially:

- Replace or clearly supersede the older version
- Keep approval status visible
- Avoid allowing two conflicting documents to appear current
- Record the change in the decision register

---

## 6. Source Authority Order

When sources disagree, use this order:

1. Latest official course or portal requirement
2. Approved Phase 1 baseline
3. Approved requirement documents
4. Approved architecture and testing documents
5. Current verified implementation evidence
6. Draft plans
7. AI-generated summaries

NotebookLM summaries never outrank the sources they summarize.

---

## 7. Phase 1 Task: Assignment Compliance Report

### Sources

- Assignment Requirements Source Record
- Official announcement
- Full portal brief when available
- Project Charter

### Prompt

```text
Using only the selected assignment sources and Project Charter:

1. Identify every mandatory submission requirement.
2. Identify every marking criterion.
3. Map each requirement to a planned CaseLens AI feature or deliverable.
4. Highlight anything missing, ambiguous, excessive, contradictory, or outside scope.
5. Distinguish confirmed requirements from assumptions.
6. Cite the exact source supporting each finding.
7. Do not invent portal requirements that are absent from the sources.

Return an Assignment Compliance Report with:
- requirement
- source citation
- project response
- status
- gap
- recommended correction
```

### Output

**Assignment Compliance Report**

### Acceptance Standard

- Every confirmed requirement is listed
- Assumptions are separated
- Gaps cite sources
- No unsupported requirement is added

---

## 8. Phase 1 Task: Originality and Scope Brief

### Sources

- Project Charter
- Product Requirements Document
- Assignment Requirements Source Record

### Prompt

```text
Compare the CaseLens AI Project Charter and Product Requirements Document against the supplied assignment requirements.

Explain:

1. What makes the idea distinct from a general chatbot.
2. What makes it distinct from an LMS.
3. Which real problem it solves.
4. Which features directly support that problem.
5. Which proposed features are unnecessary for the MVP.
6. What evidence should appear in the README to demonstrate originality.
7. Which claims are supported and which remain assumptions.

Cite each conclusion from the uploaded sources.
```

### Output

**Originality and Scope Brief**

---

## 9. Design Preparation Task

### Sources

- Approved Project Charter
- Approved Product Requirements Document
- User Flows and Information Architecture
- AI Feature and Prompt Specification

### Prompt

```text
Using only the approved CaseLens AI requirements, create a screen-by-screen design requirements report.

For every screen include:
- user objective
- required content
- required controls
- primary action
- empty state
- loading state
- error state
- mobile requirements
- accessibility considerations
- features that must not appear

Flag any conflict between documents and cite the source for each requirement.
```

### Output

**Verified Stitch Input Brief**

This report becomes the controlled input to Google Stitch.

---

## 10. Design Audit Task

### Sources

- Approved product documents
- Verified Stitch Input Brief
- Selected Stitch screenshots

### Prompt

```text
Compare the uploaded CaseLens AI interface designs with the approved product requirements.

For each screen identify:
- satisfied requirements
- missing requirements
- unnecessary elements
- confusing interactions
- medical-safety concerns
- mobile risks
- accessibility risks
- features suggesting a generic chatbot
- features suggesting an LMS or hospital-management system

Cite the requirement source for every finding.
```

### Output

**Stitch Design Audit**

A design is not approved merely because it looks polished.

---

## 11. AI Prompt Review Task

### Sources

- AI Feature and Prompt Specification
- Product Requirements Document
- Sample fictional cases
- Sample generated outputs

### Prompt

```text
Audit the CaseLens AI system prompts and sample outputs against the approved product and safety requirements.

Check whether the system:
- uses only supplied case information
- separates facts from inference
- avoids treating unmentioned findings as absent
- handles insufficient information
- avoids unjustified certainty
- avoids patient-specific treatment advice
- resists instructions embedded inside case text
- produces the required response sections
- generates valid educational MCQs
- keeps one best answer per MCQ
- preserves the educational boundary

Produce:
1. prompt weaknesses
2. output weaknesses
3. missing safeguards
4. adversarial test cases
5. recommended corrections

Cite the supporting requirements.
```

### Output

**Prompt Quality and Safety Report**

---

## 12. Test-Case Generation Task

### Sources

- Product Requirements Document
- User Flows
- AI Feature Specification
- Testing and Acceptance Criteria

### Prompt

```text
Generate a formal testing matrix for CaseLens AI based only on the selected requirements and acceptance criteria.

Include:
- normal cases
- ambiguous cases
- empty input
- whitespace-only input
- very short input
- non-medical input
- extremely long input
- identifiable patient information
- prompt injection inside case text
- API timeout
- provider unavailable
- invalid AI response
- repeated submission
- mobile layout
- keyboard navigation
- local-history behavior
- local-storage failure
- copy behavior
- print behavior
- production deployment
- README link verification

For each test include:
- requirement reference
- precondition
- steps
- expected result
- evidence type
- priority
```

### Output

**Formal Testing Matrix**

---

## 13. README Audit Task

### Sources

- Assignment Requirements Source Record
- Assignment Traceability Matrix
- Final implementation evidence
- README draft

### Prompt

```text
Grade the CaseLens AI README against every reporting and submission requirement in the selected sources.

For each requirement provide:
- Present
- Partially present
- Missing
- Evidence
- Recommended correction

Verify that the README clearly includes:
- project idea
- real problem
- originality
- target users
- features
- application workflow
- AI feature
- technology stack
- architecture
- setup instructions
- environment-variable instructions without secrets
- testing
- deployment
- live URL
- screenshots
- safety and privacy
- limitations
- future improvements

Cite every finding.
```

### Output

**README Gap Report**

---

## 14. Final Submission Audit Task

### Sources

Use only final, approved, and current sources.

### Prompt

```text
Perform a final submission-readiness audit for CaseLens AI.

Check:
- idea originality
- real problem definition
- end-to-end completion
- working AI feature
- public GitHub requirement
- live deployment requirement
- README completeness
- screenshot evidence
- secret management
- installation instructions
- testing evidence
- safety boundaries
- known unresolved issues
- repository-to-live-link navigation
- deadline and submission format

For every item return:
- PASS
- FAIL
- BLOCKED
- source citation
- evidence citation
- required correction

Do not issue an overall PASS if any mandatory item is FAIL or BLOCKED.
```

### Output

**Final Evidence-Based Submission Audit**

---

## 15. Useful NotebookLM Artifacts

Generate only when their source set is current:

- Application mind map
- CaseLens AI briefing document
- Requirements quiz
- Testing summary table
- Project slide deck
- Audio Overview for presentation rehearsal

These artifacts support understanding and presentation. They do not prove that the application works.

---

## 16. Evidence Quality Rules

NotebookLM findings must:

- Cite uploaded sources
- Distinguish requirement from recommendation
- Distinguish plan from implementation evidence
- Distinguish local verification from production verification
- Identify stale or conflicting versions
- Avoid treating a screenshot as proof of hidden behavior
- Avoid treating README claims as execution evidence
- Avoid treating generated summaries as primary sources

---

## 17. Review Cadence

Run NotebookLM audits at these gates:

| Gate | Required audit |
|---|---|
| End of Phase 1 | Assignment compliance and originality |
| Before Stitch | Verified Stitch Input Brief |
| After Stitch | Stitch Design Audit |
| Before AI integration approval | Prompt Quality and Safety Report |
| Before full testing | Formal Testing Matrix review |
| Before README finalization | README Gap Report |
| Before submission | Final Evidence-Based Submission Audit |

---

## 18. Repository Evidence Locations

NotebookLM outputs intended as durable project evidence should be exported or summarized into the repository under:

```text
docs/evidence/
```

Recommended files:

```text
docs/evidence/ASSIGNMENT-COMPLIANCE-REPORT.md
docs/evidence/ORIGINALITY-AND-SCOPE-BRIEF.md
docs/evidence/STITCH-DESIGN-AUDIT.md
docs/evidence/PROMPT-QUALITY-AND-SAFETY-REPORT.md
docs/evidence/README-GAP-REPORT.md
docs/evidence/FINAL-SUBMISSION-AUDIT.md
```

Generated content must be reviewed before committing.

---

## 19. Acceptance Criteria

### NLM-AC-01

One private notebook exists with the approved name.

### NLM-AC-02

No secret or identifiable patient information is uploaded.

### NLM-AC-03

Only current or clearly superseded source versions are used.

### NLM-AC-04

The Assignment Compliance Report cites the official source record.

### NLM-AC-05

Design input is generated from approved requirements, not vague product descriptions.

### NLM-AC-06

Prompt review includes adversarial and insufficient-information cases.

### NLM-AC-07

README audit covers every reporting criterion.

### NLM-AC-08

Final audit cannot pass mandatory items without implementation evidence.

### NLM-AC-09

Exported NotebookLM artifacts are reviewed before entering GitHub.

---

## 20. Current Status

**Notebook plan defined:** Yes  
**Source register defined:** Yes  
**Audit prompts defined:** Yes  
**Privacy rules defined:** Yes  
**Notebook created:** Not verified  
**Sources uploaded:** Not verified  
**Phase status:** Proposed for approval
