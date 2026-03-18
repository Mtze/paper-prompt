# PROMPT: A Phase-Based Platform for Administering Project-Based Courses

LaTeX source for a paper submitted to **Koli Calling 2025** (System and Tool Paper).

---

## Abstract (draft)

Project-based courses require a structured administrative lifecycle -- application, team formation,
iterative project phases, and formative assessment -- that existing learning management systems
are not designed to support.
PROMPT is an open-source course administration platform that addresses this gap by introducing a
phase-based course meta-model, in which a course is modeled as an ordered sequence of composable,
independently operable phase instances.
The platform ships with four production-ready phase implementations (Application, Interview,
Team Allocation, and Assessment) and a plugin architecture for institution-specific extensions.
The Assessment Phase uniquely formalizes formative feedback through configurable rubric-based
criteria, self-evaluation, and peer evaluation at each project milestone.
PROMPT has been deployed in production at TUM across multiple semesters for the iPraktikum
practical course.
An evaluation comprising a feature comparison, instructor interviews, and a student survey
demonstrates the adequacy of the meta-model and the usability of the platform.
PROMPT is available open-source at <https://github.com/prompt-edu/prompt>.

---

## Research Questions

| ID | Question | Method |
| --- | --- | --- |
| RQ1 | Does the phase-based meta-model adequately capture the administrative structure of project-based courses? | Feature comparison with Moodle, Canvas, GitHub Classroom, Artemis |
| RQ2 | How do instructors and TAs perceive the utility and usability of PROMPT for course administration? | Semi-structured interviews (N=5-8), thematic analysis |
| RQ3 | How effectively does the plugin architecture support institution-specific and discipline-specific extensions? | Student survey (SUS + custom items) + multi-institution deployment evidence |

---

## Paper Structure

| Section | File | Pages |
| --- | --- | --- |
| 1. Introduction | `chapters/01-introduction.tex` | 1.5 |
| 2. Background and Motivation | `chapters/02-related-work.tex` | 1.5 |
| 3. The PROMPT Platform | `chapters/03-methodology.tex` | 2.5 |
| 4. Evaluation | `chapters/04-results.tex` | 2.5 |
| 5. Discussion | `chapters/05-discussion.tex` | 1.5 |
| 6. Conclusion | `chapters/06-conclusion.tex` | 0.5 |

**Section 3 subsections**: Design Goals - Phase-Based Meta-Model - Default Phases
(Application, Interview, Team Allocation, Assessment) - Architecture - Extension System - Deployment.

---

## Key Files

| File | Purpose |
| --- | --- |
| `paper.tex` | Main document (preamble, structure, custom commands) |
| `chapters/01-introduction.tex` | Introduction |
| `chapters/02-related-work.tex` | Background and Motivation |
| `chapters/03-methodology.tex` | The PROMPT Platform |
| `chapters/04-results.tex` | Evaluation |
| `chapters/05-discussion.tex` | Discussion |
| `chapters/06-conclusion.tex` | Conclusion |
| `.claude/concept.md` | Completed paper conceptualization |
| `.claude/call-for-paper.md` | Koli Calling CFP details |
| `references.bib` | Bibliography |

---

## Building the Paper

```bash
# Compile to PDF
latexmk -pdf -interaction=nonstopmode paper.tex

# Clean auxiliary files
latexmk -c paper.tex

# Word count
texcount -inc paper.tex
```

CI compiles on every push to `main`; download the PDF from the **Actions** tab (available 30 days).

---

## Survey Instruments

The evaluation uses two instruments (see `.claude/concept.md` §5b for details):

**Student Survey**: SUS (10 items) + 13 custom Likert items covering Application Phase (3),
Team Allocation Phase (3), and Assessment Phase (7). Two open-ended questions.

**Instructor/TA Interview Protocol**: ~45 min semi-structured interview covering workflow changes,
Assessment Phase experiences, comparison with prior tools, and cross-disciplinary applicability.

---

## Target Venue

**Koli Calling 2025** - International Conference on Computing Education Research
Category: System and Tool Paper (10 pages + references, double-column ACM format, double-anonymous)
