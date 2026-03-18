# Paper Conceptualization

---

## 0. Paper Type

- [ ] Empirical study
- [x] Tool paper (a system, tool, or infrastructure artifact)
- [ ] Replication study
- [ ] Literature review
- [x] Design science (the phase-based meta-model is a conceptual contribution)
- [ ] Experience report

**If this is a tool paper, complete Section 5b in addition to Section 5a.**

---

## 1. The Problem

- [x] **Core problem**: Project-based courses require a multi-phase administrative lifecycle
  (application, team formation, iterative project work, formative assessment) that generic LMS
  and exercise platforms cannot model, forcing instructors to rely on fragile ad-hoc combinations
  of spreadsheets, email, and plugins that must be reconstructed every semester.

- [x] **Who is affected**: Instructors and TAs managing large project-based courses across
  disciplines (computing, engineering, design, business); particularly acute for courses with
  >30 students, multiple project teams, external clients, and milestone-based assessment.

- [x] **Current pain**: No unified view of the course lifecycle; recurring manual effort per
  semester; lack of process consistency across iterations; poor transparency for students;
  assessment criteria communicated informally rather than formalized through tooling.

- [x] **Timeliness**: Project-based learning is expanding across universities and disciplines;
  no open-source platform has addressed the course administration gap despite growing demand
  and widespread adoption of PBL pedagogies.

---

## 2. The Gap

- [x] **Existing approaches**: Moodle, Canvas (LMS); Artemis, GitHub Classroom (exercise
  platforms); ad-hoc combinations of Google Forms, spreadsheets, Jira.

- [x] **Their shortcomings**: LMS model courses as flat content hierarchies -- no phase
  lifecycle, no team structures, no pass/fail decisions per phase, no formative feedback
  infrastructure. Exercise platforms optimize for individual submission grading. Ad-hoc tools
  lack consistency and require per-semester manual re-setup.

- [x] **The precise gap**: No existing open-source platform provides a composable, phase-based
  course meta-model that enables instructors to model the administrative lifecycle of any
  project-based course as an ordered sequence of independently operable phase modules.

---

## 3. Core Contribution

- [x] **One-sentence contribution**: "This paper contributes PROMPT, a phase-based course
  meta-model and its open-source implementation, which enables instructors to administer
  project-based courses as composable sequences of independently operable phase modules,
  applicable across disciplines."

- [x] **Contribution type**:
  - [x] New tool or infrastructure
  - [x] New framework, model, or taxonomy (the phase-based meta-model)

- [x] **Novelty argument**: Existing tools either model courses as flat content repositories
  (LMS) or optimize for individual assessment workflows (exercise platforms). PROMPT introduces
  the course lifecycle as a first-class composable structure -- a design abstraction absent from
  all comparable tools. The Assessment Phase additionally formalizes formative feedback
  (self-evaluation, peer evaluation, configurable rubric criteria) in a way no existing course
  administration tool does.

- [x] **Significance**: Reduces per-semester administrative overhead; enables reproducible
  course processes; provides students with transparent, formalized assessment criteria;
  the domain-agnostic meta-model is reusable across disciplines; the open-source implementation
  is immediately deployable by any institution.

---

## 4. Research Questions

- [x] **RQ1**: Does the phase-based meta-model adequately capture the administrative structure
  of project-based courses?
  - How answered: Feature comparison table (PROMPT vs. Moodle, Canvas, GitHub Classroom, Artemis)
    against 10 project-course administrative capabilities + multi-semester deployment evidence.

- [x] **RQ2**: How do instructors and TAs perceive the utility and usability of PROMPT for
  managing project-based course administration?
  - How answered: 5-8 semi-structured instructor/TA interviews, thematic analysis
    (Braun & Clarke, 2006).

- [x] **RQ3**: How effectively does the plugin architecture support institution-specific and
  discipline-specific extensions without modifying the platform core?
  - How answered: Student survey (SUS + 13 custom Likert items, especially Assessment Phase)
    + multi-institution deployment evidence.

- [x] **Coherence check**: RQ1 validates meta-model design adequacy; RQ2 validates practical
  usability and utility; RQ3 validates extensibility and formative assessment features.
  Together they cover design adequacy, practical utility, and generalizability.

---

## 5a. Methodology (All Paper Types)

- [x] **Research method**:
  - [x] Design science / artifact construction (the platform itself)
  - [x] User study / survey (student survey)
  - [x] Interview study (instructor/TA interviews)
  - [x] Feature comparison (documentary/analytical)

- [x] **Data / participants**: 5-8 TUM instructors/TAs (interviews); N iPraktikum students
  (survey); 5 tools (feature comparison: PROMPT, Moodle, Canvas, GitHub Classroom, Artemis).

- [x] **Evaluation plan**: (1) feature comparison table against 10 capabilities; (2) thematic
  analysis of interview transcripts; (3) SUS score + Likert means/SD from student survey;
  (4) deployment statistics (semesters, students, institutions).

- [x] **Baseline / comparison**: Moodle, Canvas, GitHub Classroom, Artemis.

- [x] **Statistical approach**: Descriptive statistics for survey (mean, SD, SUS score);
  thematic analysis for interviews (open coding, axial coding, theme saturation check);
  inter-rater reliability via Cohen's kappa on 20% sample.

- [x] **Ethical considerations**: Participant consent required for interviews and survey;
  data anonymized before reporting; check TUM ethics review requirements before data collection.

---

## 5b. Methodology - Tool Papers

### Tool Description

- [x] **Tool name and purpose**: PROMPT -- an open-source course administration platform
  implementing a phase-based course meta-model for project-based courses of any discipline.

- [x] **Target users**: Instructors and TAs managing project-based university courses;
  students interacting with course administration processes (applications, team assignments,
  feedback).

- [x] **Implementation**: Frontend: React + TypeScript, Webpack Module Federation
  (micro-frontend architecture). Backend: Go microservices (one per phase), PostgreSQL,
  Keycloak authentication. Infrastructure: Docker/Kubernetes. Shared libraries: prompt-sdk
  (Go), prompt-lib (React).

- [x] **Architecture**: Micro-frontend shell dynamically loads per-phase micro-frontends at
  runtime via Webpack Module Federation. Each phase = independent Go microservice + React
  micro-frontend. Keycloak provides centralized authentication and role management. Each phase
  has an independent PostgreSQL schema.

- [x] **Maturity level**: Production-ready -- deployed at TUM for multiple semesters,
  supporting 100+ students per semester in the iPraktikum practical course.

### Tool Evaluation

- [x] **Correctness**: Multi-semester production deployment at TUM provides implicit operational
  validation; feature comparison demonstrates alignment with project-course requirements.

- [x] **Performance**: Production deployment at TUM scale (100+ students, parallel project
  teams) demonstrates sufficient scalability; not a primary evaluation focus.

- [x] **Usability**: Instructor interviews (qualitative, 5-8 participants) +
  student SUS survey (quantitative, target N=50+).

- [x] **Comparison**: Feature comparison table -- PROMPT vs. Moodle, Canvas, GitHub Classroom,
  Artemis on 10 project-course administrative capabilities using a three-level scale
  (native / partial / not supported).

### Demo / Presentation

- [x] **Demo scenario**: iPraktikum course lifecycle walkthrough: student applies via
  Application Phase -> tutors conduct structured interviews via Interview Phase -> teams formed
  via Team Allocation Phase with TEASE optimization -> three Assessment Phases at project
  milestones with self-evaluation, peer evaluation, and instructor rubric assessment.

- [x] **Demo video**: Not required by Koli; optional supplementary material.

- [x] **Live demo**: Consider for conference presentation -- the live instance at
  prompt.aet.cit.tum.de supports this.

---

## 6. Paper Story / Narrative

- [x] **One-paragraph story**: "Instructors of large project-based courses face a recurring
  administrative burden: every semester they reconstruct ad-hoc workflows from spreadsheets,
  email chains, and LMS plugins to manage applications, team formation, and assessment --
  tools never designed for this purpose. PROMPT solves this by introducing the phase-based
  course meta-model, which treats the course lifecycle as a first-class composable structure.
  The four default phases cover the most common administrative needs, and the Assessment Phase
  uniquely formalizes formative feedback through configurable criteria, self-evaluation, and
  peer evaluation -- a pedagogical contribution absent from all comparable tools. Instructor
  interviews confirm reduced administrative overhead; student survey results show high usability
  and strong appreciation of the Assessment Phase's transparency. The meta-model's
  domain-agnostic design means these benefits extend beyond computing education to any
  project-based course."

- [x] **The "aha" moment**: The Assessment Phase as a formalized formative feedback mechanism
  -- not just an administrative tool but a pedagogical one. No other course administration tool
  provides configurable rubric criteria with self-evaluation, peer evaluation, and instructor
  assessment in a unified workflow at each milestone.

- [x] **Null result scenario**: If adoption is only TUM, the paper remains publishable as a
  deep single-institution case study with strong qualitative evidence. The meta-model
  contribution stands independently of adoption breadth.

- [x] **Title candidates**:
  1. "PROMPT: A Phase-Based Platform for Administering Project-Based Courses"
  2. "A Phase-Based Course Meta-Model for Project-Based Education: Design and Evaluation of PROMPT"
  3. "PROMPT: Composable Phase-Based Course Administration for Project-Based Learning"

---

## 7. Related Work Positioning

- [x] **Moodle** (Dougiamas & Taylor, 2003) -> PROMPT differs: Moodle models courses as
  content hierarchies; no phase lifecycle, no team structures, no phase-specific workflows.
  Moodle plugins exist for some features but require per-course manual assembly with no
  unified lifecycle model.

- [x] **Artemis** (Krusche & Seitz, 2018) -> PROMPT differs: Artemis is optimized for
  individual exercise grading and automated feedback in computing education; PROMPT manages
  the organizational lifecycle of project teams. The two tools are complementary, not competing.
  Critical to address explicitly since both originate from TUM.

- [x] **GitHub Classroom** -> PROMPT differs: GitHub Classroom automates repository creation
  for team-based projects but has no administrative workflow model beyond repository setup and
  assignment distribution.

- [x] **Canvas** -> PROMPT differs: same structural limitations as Moodle; enterprise focus,
  not open-source.

- [x] **TEASE** -> PROMPT integrates TEASE for team allocation; TEASE addresses one specific
  administrative task, PROMPT addresses the full course lifecycle.

- [x] **Positioning statement**: "Unlike LMS platforms that model courses as flat content
  hierarchies, and unlike programming exercise platforms that optimize for individual assessment
  workflows, PROMPT introduces a phase-based course meta-model that treats the course lifecycle
  as a first-class composable structure -- applicable to any project-based course regardless
  of discipline."

---

## 8. Target Audience

- [x] **Primary readers**: CS education researchers and practitioners at Koli; instructors
  of project-based courses seeking tool support; tool builders in the education technology space.

- [x] **Takeaway**: A ready-to-deploy open-source platform for project-based course
  administration; an understanding of the phase-based meta-model as a reusable abstraction;
  a survey instrument and interview protocol for evaluating course administration tools.

- [x] **Secondary audience**: Instructors outside CS (engineering, design, business) who face
  the same administrative challenges; researchers studying formative assessment in PBL contexts.

---

## 9. Scope and Anticipated Limitations

- [x] **In scope**: Administrative lifecycle of project-based courses; PROMPT platform design
  and default phases; usability and utility from instructor and student perspectives; feature
  comparison with existing tools.

- [x] **Out of scope**: Learning outcomes assessment; LMS features unrelated to project course
  administration; automated grading (not a PROMPT feature by design).

- [x] **Threats to internal validity**: Feature comparison criteria self-selected by authors
  (bias toward capabilities PROMPT provides); interview participants all known PROMPT users
  from TUM (selection bias); survey instrument designed by authors (instrument bias).

- [x] **Threats to external validity**: Evaluation limited to TUM and iPraktikum; no empirical
  cross-disciplinary validation; findings may not generalize to smaller courses, non-European
  institutions, or non-team-based project courses.

- [x] **Threats to construct validity**: SUS measures perceived usability, not task performance;
  custom Likert items lack external validation; interview themes reflect perceptions rather than
  behavioral data; time savings are instructor estimates, not measured values.

- [x] **Mitigation strategies**: Use three-level scale in feature comparison; report SUS
  alongside custom items; follow Braun & Clarke protocol; calculate inter-rater reliability;
  acknowledge all threats in Discussion.

---

## 10. Venue Fit

- [x] **Why this venue**: Koli Calling is the premier European computing education conference;
  the System and Tool Paper category is an exact match; Koli's intimate atmosphere (single-track)
  suits a tool presentation with live demo potential.

- [x] **CFP alignment**: "Development, use, and evaluation of tools to support computing
  education" -- direct match. "Teaching approaches and assessment in computing education" --
  matches the Assessment Phase contribution.

- [x] **Format fit**: System and Tool Paper, 10 pages + references, ACM double-column.
  Confirmed match.

- [x] **Page budget sketch**:
  - Introduction: 1.5p
  - Background and Motivation: 1.5p
  - The PROMPT Platform: 2.5p
  - Evaluation: 2.5p
  - Discussion: 1.5p
  - Conclusion: 0.5p
  - References: ~1-2p (excluded from limit)
  - Total: 10p / 10p allowed

---

## 11. Replication Package

### Content

- [x] **Raw data**: Anonymized interview transcripts (pending consent); anonymized survey
  response data.

- [x] **Processed data**: Coded themes from interviews; aggregated survey statistics;
  feature comparison scoring rationale.

- [x] **Code / scripts**: PROMPT platform source code (public at
  https://github.com/prompt-edu/prompt); analysis scripts for survey data.

- [x] **Documentation**: Interview guide, survey instrument, feature comparison methodology.

- [x] **Supplementary material**: Full feature comparison table; full interview protocol;
  full survey instrument.

### Sharing Constraints

- [x] **Privacy / ethics**: Interview and survey data anonymized before release; participant
  consent required for any transcript sharing.

- [x] **Anonymization**: Participant identifiers removed; institution details generalized
  where needed for blind review.

- [x] **Licensing**: MIT (platform code, already open-source); CC BY 4.0 (research data and
  instruments).

### Hosting and Availability

- [x] **Repository**: GitHub (platform code) + Zenodo (research data, instruments, analysis
  scripts).

- [x] **Persistent identifier**: Zenodo DOI for research data package.

### Artifact Evaluation

- [x] **AE track**: Koli Calling does not have a formal AE track; open-source availability
  with deployment instructions serves as the artifact contribution.

- [x] **Target badges**: Artifacts Available (GitHub + Zenodo); Artifacts Functional
  (live deployment at prompt.aet.cit.tum.de).

---

## 12. Readiness Check

- [x] The core problem is stated in one precise sentence.
- [x] The gap is distinct from "related work exists."
- [x] The contribution is stated in one sentence with a clear novelty argument.
- [x] All research questions are specific and answerable with the planned methodology.
- [x] The methodology matches the research questions.
- [x] The paper story is written as a coherent paragraph.
- [x] The 3-5 closest related papers are identified and differentiation is clear.
- [x] The replication package content is planned and sharing constraints are known.
- [x] The page budget is sketched and fits the venue's limit.
- [x] Tool architecture, evaluation, and demo scenario are defined.

**Ready to write? Yes** -- all boxes checked.
