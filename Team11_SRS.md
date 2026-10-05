# Software Requirements Specification
## [Project Name]

**Team:** [Team Name]  
**Authors:** [Name 1], [Name 2], [Name 3], [Name 4]  
**Version:** 1.0  
**Date:** 2026-10-07

---

# 1. Purpose

## 1.1 Background


Students at universities (ex.KAIST) face significant difficulties when planning their academic roadmap. They must cross-reference static PDF bulletins (학사요람), tools such as the OTL (Online Timetable and Lectures) Graduation Planner, separate GPA spreadsheets, and course-review portals.

This fragmented workflow causes three problems:

1. **Error-prone manual audits.** Checking completed courses against graduation requirements (major requirements, research credits, elective distributions) one by one is easy to get wrong.
2. **No future GPA simulation.** Existing planners cannot simulate future GPA under different letter-grade scenarios, so students maintain separate spreadsheets or online calculators.
3. **Lack of help with target GPAs.** Students aiming for a specific cutoff (graduate admission, honors, scholarships) have no tool that tells them which letter grades they need through their remaining courses.

This project addresses these problems by combining degree-audit validation, transcript import, forward-looking GPA simulation, and course planning in a single real-time tool.

## 1.2 System Overview

**(name)**  is an integrated academic planner and GPA simulator built around university degree programs. Its main functions are:

- **Transcript import and semester view.** Imports past academic records and lists completed courses by semester, with final grades and credits.

- **Rules-based graduation audit.** Checks completed and planned courses against the requirements for the student's admission year. Shows progress per category (e.g., Major Required: 9/12 credits) and names exactly which required courses are still missing, according to the student's track (major, minor).

- **Future-semester planning & live GPA simulation.** Lets users create future semesters, choose their planned courses, assign projected letter grades, and see cumulative and major GPA update instantly.

- **Target GPA solver.** Given a desired final GPA, computes the average grade needed across the courses without a grade yet, and suggests letter-grade combinations that achieve it (e.g., how many A+ and A0 are needed).

- **(optional) AI course advisor .** Uses an LLM (e.g., Google Gemini), grounded in course data and OTL student reviews, to recommend courses that fill remaining graduation gaps and match the student's preferences.

## 1.3 Scope

### In Scope

- **Transcript import.** Extracting course codes, titles, credits/AU, and letter grades from a transcript the user provides (file or text upload) or from the academic portal page the user is logged into.

- **Requirement engine.** A configurable rules engine based on the academic bulletin, supporting the primary major and minor, with requirements that vary by admission year (이수요건). (Double-major support can be added as an extension.)

- **Multi-semester planner.** An interface for adding future semesters, selecting courses, and categorizing credit types.

- **Real-time GPA engine.** Recalculates semester, cumulative, and major GPA on the university's grade scale (4.3 scale; a 4.0 scale can be supported), excluding S/U courses from GPA and handling retakes.

- **Reverse grade solver.** Calculates the required average grade point for the ungraded courses and generates letter-grade combinations that reach the target.

- **(optional)AI course recommendation.** Recommendations based on search over course descriptions and OTL reviews.

### Out of Scope

- **Course registration.** The system will not register, add, or drop courses, or log into the official registration system.

- **Official audit or certification.** The system gives unofficial planning guidance only. Final graduation approval remains with the university's academic affairs office.

- **Storing portal credentials.** The system will not store university portal passwords. Transcript import uses a client-side session, OAuth (if available), or a file/text upload initiated by the user.

- **LMS integration.** No integration with systems such as KLMS for attendance or assignment tracking.

## 1.4 Definitions and Terminology

| Term | Definition |
|---|---|
| **OTL** | Online Timetable and Lectures. The open-source course timetable, review, and graduation-planning service at KAIST. |
| **Academic Bulletin (학사요람)** | The official document that defines required curriculum, category minimums, and graduation criteria for each admission year and major. |
| **Graduation Audit** | A checklist that sorts courses into graduation categories (Major Required, Major Elective, Basic Required, Humanities, Research, etc.) and tracks completion. |
| **GPA** | Credit-weighted average of grade points, usually on a 4.3 scale. |
| **Target GPA Solver** | Determines the average grade needed on the remaining courses, and the combinations of letter grades that reach a user-defined target GPA. |
| **Letter-Grade Combination** | A breakdown of the remaining credits into achievable letter grades (e.g., "two A0s and one B+ across your 9 ungraded credits"). |

## 1.5 References

- KAIST Academic Bulletin (학사요람)
- KAIST Academic System Portal
- Google Gemini API documentation

# 2. Overall Description

## 2.1 Product Perspective

<!--
How does this product fit into the outside world?
Is it standalone? Web-based? Does it communicate with another system?
-->

[Describe the context in which the system operates.]

### 2.1.1 System Interfaces

<!-- External systems that this software interacts with. -->

- [External System A]: ...
- [External System B]: ...

### 2.1.2 User Interfaces

<!--
Describe the required user-facing interfaces at a high level.
Detailed visual design is NOT necessary unless appearance itself
is a requirement.
-->

The system shall provide the following major interfaces:

- [Main screen]: ...
- [Settings screen]: ...
- [Other interface]: ...

### 2.1.3 Hardware Interfaces

<!-- Delete this subsection if irrelevant. -->

[Describe required hardware interactions.]

### 2.1.4 Software Interfaces

<!-- Delete this subsection if irrelevant. -->

[Describe required APIs, file formats, protocols, etc.]

### 2.1.5 Communication Interfaces

<!-- Delete this subsection if irrelevant. -->

[Describe networking / communication requirements.]

## 2.2 Product Functions

<!--
High-level summary only.
Detailed requirements belong in Section 3.
-->

The major functions of the system are:

1. **[Function A]**
   - [Short description]

2. **[Function B]**
   - [Short description]

3. **[Function C]**
   - [Short description]

## 2.3 User Characteristics

### [User Type A]

- Expected knowledge: ...
- Typical goals: ...
- Expected usage: ...

### [User Type B]

- Expected knowledge: ...
- Typical goals: ...
- Expected usage: ...

## 2.4 Constraints

<!--
Only actual constraints.
Do NOT make arbitrary implementation decisions here.
-->

- The system shall ...
- The system must operate on ...
- The system shall comply with ...

## 2.5 Assumptions and Dependencies

- It is assumed that ...
- The system depends on ...
- [External service] is assumed to ...

---

# 3. Specific Requirements

# 3.1 Functional Requirements

<!--
Give every important requirement a stable identifier.
Prefer requirements that can eventually be tested as pass/fail.

Recommended form:
"The system shall ..."

Avoid:
"The system should be convenient."
"The UI should be intuitive."
"The system should be fast."
-->

## FR-1: [Feature Name]

**Description:**  
[Brief description of the feature.]

**Requirements:**

- **FR-1.1:** The system shall ...
- **FR-1.2:** The system shall ...
- **FR-1.3:** The system shall ...

**Preconditions:**

- ...

**Postconditions:**

- ...

**Failure / Edge Cases:**

- If ..., the system shall ...
- If ..., the system shall ...

---

## FR-2: [Feature Name]

**Description:**  
...

**Requirements:**

- **FR-2.1:** The system shall ...
- **FR-2.2:** The system shall ...
- **FR-2.3:** The system shall ...

**Preconditions:**

- ...

**Postconditions:**

- ...

**Failure / Edge Cases:**

- ...

---

## FR-3: [Feature Name]

...

---

# 3.2 External Interface Requirements

## 3.2.1 User Interface Requirements

- **UI-1:** The system shall ...
- **UI-2:** The system shall ...
- **UI-3:** The system shall ...

## 3.2.2 External Software Interface Requirements

- **INT-1:** The system shall ...
- **INT-2:** The system shall ...

---

# 3.3 Data Requirements

<!--
What information must exist and what properties must it have?
Describe logical requirements rather than choosing a DB schema.
-->

## 3.3.1 [Entity / Data Type]

The system shall store:

- ...
- ...
- ...

Requirements:

- **DATA-1:** ...
- **DATA-2:** ...

## 3.3.2 Data Persistence

- **DATA-3:** The system shall ...
- **DATA-4:** The system shall ...

---

# 3.4 Performance Requirements

<!--
Use measurable requirements where performance actually matters.
Do not invent benchmark numbers for things nobody cares about.
-->

- **PERF-1:** The system shall ...
- **PERF-2:** Under [condition], the system shall ...
- **PERF-3:** The system shall support at least ...

---

# 3.5 Software System Attributes

## 3.5.1 Reliability

- **REL-1:** The system shall ...
- **REL-2:** ...

## 3.5.2 Availability

<!-- Delete if irrelevant. -->

- **AVL-1:** ...

## 3.5.3 Security and Privacy

- **SEC-1:** The system shall ...
- **SEC-2:** The system shall not ...
- **SEC-3:** ...

## 3.5.4 Maintainability

<!--
Only include externally meaningful maintainability requirements.
Detailed architecture belongs in the SDD.
-->

- **MAINT-1:** ...

## 3.5.5 Portability

- **PORT-1:** The system shall run on ...
- **PORT-2:** ...

---

# 3.6 Environment Requirements

## 3.6.1 Supported Platforms

- ...
- ...

## 3.6.2 Required Environment

- ...
- ...

---

# 4. Use Cases

## UC-1: Plan Future Semesters with Instant GPA Simulation

- **Primary Actor:** Student (User)
- **Goal:** Add future semesters, select planned courses, and input or adjust expected grades to receive real-time updates on semester/ cumulative/major GPAs, as well as graduation requirement progress.
- **Preconditions:**
  1. The user's past course history (confirmed grades) is loaded/manually entered.
  2. The user's department, admission year, and degree track (e.g., single major, minor) are configured according to the Academic Bulletin.
- **Trigger:** The user adds a planned semester or modifies an expected grade (e.g., A+, B0) for a planned course.
- **Main Flow:**
  1. The user adds a future semester (e.g., "Fall 2026") and selects courses to take.
  2. The system categorizes each course into its graduation requirement bucket (e.g., Major Required, Major Elective, Basic Required) and updates graduation progress bars (e.g., Major Required: 9/12 credits) along with the list of remaining mandatory courses.
  3. The user assigns anticipated letter grades to some or all of the planned courses, leaving others blank.
  4. The system recalculates semester GPA, cumulative GPA, and major GPA instantly on the 4.3 scale.
  5. The user experiments with different letter-grade combinations, observing instant updates to both GPA metrics & degree requirements.
- **Alternative / Failure Flows:**
  - **A1: Course Graded on S/U (Pass/Fail)**
    1. The user adds a course that does not carry numeric grade points (e.g., physical education or research).
    2. The system excludes the course from GPA calculations while counting its credits toward total graduation completion upon a passing grade.
- **Postconditions:**
  1. The planned semester roadmap and simulated GPA metrics are updated and persisted in the user's active session.
- **Related Requirements:** -

---

## UC-2: Grade Distribution for Target GPA

- **Primary Actor:** Student (User)
- **Goal:** Obtain the required average grade point and concrete letter-grade combinations (e.g., two A+ grades and one A0) across future courses to achieve a desired target GPA.
- **Preconditions:**
  1. Historical courses have confirmed grades.
  2. At least one planned future course has its grade left blank (unassigned).
- **Trigger:** The user enters a target GPA (e.g., 3.70 / 4.30) and requests grade distribution calculation.
- **Main Flow:**
  1. The user inputs their desired target GPA.
  2. The system checks all pending courses with unassigned grades and sums their credit hours.
  3. The system calculates the minimum average grade point needed across those remaining credits to reach the target.
  4. The system calculates letter-grade combinations (A+, A0, A-, B+, etc.) that meet or exceed the target.
  5. The system displays the required average grade point along with feasible letter-grade scenarios (e.g., "Option 1: 2x A+ and 1x A0", "Option 2: 3x A+ and 1x B+").
- **Alternative / Failure Flows:**
  - **A1: Impossible Target GPA**
    1. The required grade point exceeds the maximum possible score (4.30).
    2. The system notifies the user that the target cannot be reached and displays the highest possible GPA achievable even with straight A+ grades.
  - **A2: Target Already Guaranteed**
    1. The required average grade point is at or below the minimum passing grade (D- / 0.70).
    2. The system informs the user that receiving minimum passing grades in all remaining courses is enough to reach the goal.
- **Postconditions:**
  1. The student receives grade goals and letter-grade scenarios to plan their upcoming semesters.
- **Related Requirements:** -s

# 5. Verification and Acceptance Criteria

<!--
For each important requirement or feature,
state how the client can determine whether it has been satisfied.

This can later become the basis for acceptance testing.
-->

| ID | Requirement | Acceptance Criterion |
|----|-------------|----------------------|
| FR-1.1 | [Summary] | [Observable pass/fail condition] |
| FR-1.2 | [Summary] | [Observable pass/fail condition] |
| FR-2.1 | [Summary] | [Observable pass/fail condition] |
| PERF-1 | [Summary] | [Measurement and threshold] |

---

# Appendix A. UI Mockups

<!--
Optional but strongly useful if UI behavior is important.

Insert images / wireframes here and refer to them from requirements.
-->

## A.1 [Screen Name]

![Mockup](path/to/mockup.png)

Description:

- ...
- ...

---

# Appendix B. Open Questions

<!--
Ideally empty before final submission.
Useful while drafting the SRS.
-->

- [ ] ...
- [ ] ...
