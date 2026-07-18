# CaseLens AI

## Assignment Requirements Source Record

### Document Control

**Project:** CaseLens AI  
**Document:** Assignment Requirements Source Record  
**Version:** 1.0  
**Status:** Source Baseline  
**Date:** 18 July 2026  
**Deadline:** Monday, 27 July 2026, 11:59 PM PKT  
**Submission Item:** Public GitHub repository link  

---

## 1. Purpose

This document preserves the assignment information supplied for the ACT AI Final Course Project and converts it into controlled requirement identifiers.

It is the primary source for Phase 1 assignment compliance until a more detailed portal brief is supplied.

The project team must not rely on memory, screenshots scattered across chats, or assumptions that a requirement probably exists. Every implementation and reporting decision must trace back to this record or to a later approved source update.

---

## 2. Source Information

### Source Type

Official course announcement supplied by the student.

### Issuing Organization

Team ACT AI | HEC × AI SkillBridge × PMYP

### Audience

ACT AI Students, Batch 1 and Batch 2.

### Source Date

Not stated in the announcement.

### Source Completeness

The announcement states that the Assignments tab contains a full brief. That full portal brief has not yet been supplied to the repository.

Therefore:

- The requirements below are confirmed from the announcement.
- Any additional portal-only requirements remain unknown.
- This record must be updated if the full portal brief is later provided.

---

## 3. Preserved Assignment Announcement

> Build a complete, working app of your own idea, one that solves a real problem, and ship it end to end.
>
> Required:
>
> - An original idea, with no copies or templates
> - A fully functional app with an AI-powered feature
> - Code in a public GitHub repository
> - The app deployed live at a public URL
> - A comprehensive README that serves as the full project report
>
> Students may use any tools.
>
> Marking criteria:
>
> 1. Idea
> 2. Completion
> 3. Deployment
> 4. Reporting through the README
>
> Deadline:
>
> Monday, 27 July 2026, 11:59 PM PKT
>
> Submission:
>
> Submit only the public GitHub repository link on the portal.

---

## 4. Confirmed Mandatory Requirements

### AR-01: Original Idea

The project must present an original application idea.

**Pass condition:** The README and application clearly explain what makes CaseLens AI distinct from a general chatbot, copied tutorial, template, or learning-management system.

**Failure condition:** The application is primarily a clone, template reskin, or generic AI chat interface without a distinct product workflow.

---

### AR-02: Real Problem

The application must solve a real and clearly explained problem.

**Pass condition:** The project identifies the difficulty medical learners face when analysing cases systematically and demonstrates how the application addresses that problem.

**Failure condition:** The project presents technology without a meaningful user problem.

---

### AR-03: Complete Working Application

The project must be a complete, working application.

**Pass condition:** A user can complete the intended end-to-end workflow from case entry through structured analysis, MCQ practice, and revision actions.

**Failure condition:** The application contains disconnected mock screens, unfinished critical features, broken workflows, or placeholder output.

---

### AR-04: AI-Powered Feature

The application must contain a functional AI-powered feature.

**Pass condition:** The deployed application sends an educational case through a protected server-side route to Gemini and receives validated structured analysis or MCQs.

**Failure condition:** AI is described but not functional, simulated through static responses, or inaccessible in production.

---

### AR-05: Public GitHub Repository

The source code must be placed in a public GitHub repository.

**Pass condition:** The repository is publicly accessible and contains the complete final source at submission time.

**Failure condition:** The repository is private, incomplete, inaccessible, or missing the final application code.

---

### AR-06: Public Deployment

The application must be deployed live at a public URL.

**Pass condition:** The production application opens without repository access or local setup and the real AI workflow functions.

**Failure condition:** Only screenshots, localhost instructions, or a broken deployment are supplied.

---

### AR-07: Comprehensive README

The README must serve as the complete project report.

**Pass condition:** The README explains the idea, problem, features, originality, AI implementation, architecture, setup, testing, deployment, screenshots, safety, limitations, and live URL.

**Failure condition:** The README is a short installation note or omits evidence required to understand and evaluate the project.

---

### AR-08: Repository-Link Submission

Only the public GitHub repository link is submitted through the portal.

**Pass condition:** The repository README prominently contains the live application URL and all reporting evidence so the evaluator can reach everything from the submitted repository.

**Failure condition:** Essential evidence exists only outside the repository or requires a second submission link.

---

### AR-09: Deadline

The project must be submitted no later than Monday, 27 July 2026, 11:59 PM PKT.

**Pass condition:** The public repository is submitted before the deadline and the linked deployment remains functional.

**Failure condition:** Submission occurs after the deadline or the repository points to an unfinished state.

---

## 5. Marking Criteria

### MC-IDEA: Idea

The project should demonstrate:

- A specific real-world problem
- A clearly defined target user
- Original product thinking
- Appropriate use of AI
- Clear distinction from common templates and general chatbots

### MC-COMPLETION: Completion

The project should demonstrate:

- A complete primary workflow
- Working input validation
- Working AI analysis
- Working MCQ generation
- Safe error handling
- Responsive behavior
- No unresolved submission-blocking defect

### MC-DEPLOYMENT: Deployment

The project should demonstrate:

- A successful production build
- A stable public URL
- Production environment variables
- Working Gemini requests in production
- No exposed secrets
- Verification on mobile and desktop

### MC-REPORTING: Reporting

The README should demonstrate:

- Clear project explanation
- Feature documentation
- Technical implementation
- Setup and deployment instructions
- Screenshots
- Testing evidence
- Safety and privacy boundaries
- Known limitations
- Live URL and repository structure

---

## 6. Derived Project Constraints

The following constraints are derived directly from the confirmed assignment requirements:

### CON-01: Completion Over Breadth

A smaller complete application is more valuable than a broad application with several unfinished features.

### CON-02: The AI Feature Must Be Visible

The AI capability must be part of the principal user journey and not an optional decorative page.

### CON-03: Repository as Submission Hub

Because only the repository link is submitted, the repository must link to the deployment and contain the complete report.

### CON-04: Public-Safe Repository

No secret, API key, patient identifier, or private credential may exist in the public repository or its history.

### CON-05: Deployment Must Be Verified

A successful local run does not satisfy the deployment criterion.

### CON-06: README Is a Graded Deliverable

README work is part of the project, not a final-hour administrative task.

---

## 7. Unknown Portal Requirements

The following remain unverified because the full portal brief has not been supplied:

- Whether a specific framework is required
- Whether a database is mandatory
- Whether authentication is mandatory
- Whether a specific number of screens is required
- Whether tests must use a named framework
- Whether a presentation or demonstration video is required
- Whether screenshots have a required count or format
- Whether individual or team attribution rules apply
- Whether external APIs have restrictions
- Whether the README must use a prescribed heading structure
- Whether code history or minimum commit count is assessed

These unknowns must not be silently converted into requirements.

---

## 8. Source Update Procedure

When a new official source is supplied:

1. Preserve the source title and date.
2. Compare it against this record.
3. Add new requirements with stable IDs.
4. Record contradictions or superseded statements.
5. Update the Assignment Traceability Matrix.
6. Update affected product and testing documents.
7. Reapprove the Phase 1 baseline if the change is material.

---

## 9. Current Source Status

**Official announcement preserved:** Yes  
**Confirmed mandatory requirements extracted:** Yes  
**Marking criteria extracted:** Yes  
**Deadline recorded:** Yes  
**Submission method recorded:** Yes  
**Full portal brief available:** No  
**Requirement baseline status:** Approved against supplied announcement, subject to later portal-brief reconciliation
