# Paper Conceptualization

Complete this document before writing.
Work through each section in order — later sections build on earlier ones.
Claude will use this file as context throughout the writing process.

---

## 0. Paper Type

Select all that apply:

- [ ] Empirical study (qualitative or quantitative investigation)
- [ ] Tool paper (a system, tool, or infrastructure artifact)
- [ ] Replication study (reproducing or extending prior work)
- [ ] Literature review / mapping study
- [ ] Design science (framework, model, method)
- [ ] Experience report / case study

**If this is a tool paper, complete Section 5b in addition to Section 5a.**

---

## 1. The Problem

> Define the problem precisely. A vague problem leads to a vague paper.

- [ ] **Core problem**: _What specific problem does this paper address?_

- [ ] **Who is affected**: _Who faces this problem, in what context, and how often?_

- [ ] **Current pain**: _What goes wrong or is impossible without solving this problem?_

- [ ] **Timeliness**: _Why is now the right time to address this? What has changed?_

---

## 2. The Gap

> Distinguish between "related work exists" and "the specific gap your work fills".

- [ ] **Existing approaches**: _What solutions or studies already address this problem area?_

- [ ] **Their shortcomings**: _Where do they fall short — in scope, correctness, scale, context, or method?_

- [ ] **The precise gap**: _In one sentence: what is missing from the current body of knowledge or tooling?_

---

## 3. Core Contribution

> If you can only say one thing about this paper, what is it?

- [ ] **One-sentence contribution**: _Complete this: "This paper contributes X, which enables/shows/demonstrates Y."_

- [ ] **Contribution type** (tick one):
  - [ ] New empirical evidence
  - [ ] New technique or algorithm
  - [ ] New tool or infrastructure
  - [ ] New framework, model, or taxonomy
  - [ ] Replication or negative result
  - [ ] Other: ___

- [ ] **Novelty argument**: _What makes this contribution new compared to the closest prior work?_

- [ ] **Significance**: _Why should the research community care? What does this change?_

---

## 4. Research Questions

> Write RQs before designing the methodology. Each RQ must be answerable.

- [ ] **RQ1**: _State the question._
  - How will it be answered? ___

- [ ] **RQ2**: _State the question._
  - How will it be answered? ___

- [ ] **RQ3** _(if applicable)_: _State the question._
  - How will it be answered? ___

- [ ] **Coherence check**: Do all RQs together address the stated gap? ___

---

## 5a. Methodology (All Paper Types)

> Match the method to the research questions.

- [ ] **Research method** (tick one):
  - [ ] Controlled experiment
  - [ ] User study / survey
  - [ ] Case study (single or multiple)
  - [ ] Mining software repositories (MSR)
  - [ ] Systematic literature review / mapping study
  - [ ] Design science / artifact construction
  - [ ] Interview study
  - [ ] Other: ___

- [ ] **Data / participants / systems**: _What material is needed to conduct the study?_

- [ ] **Evaluation plan**: _How will results be measured or validated?_

- [ ] **Baseline / comparison**: _What does the approach or result get compared against?_

- [ ] **Statistical approach**: _What statistical tests or qualitative analysis methods will be used?_

- [ ] **Ethical considerations**: _Are there IRB requirements, consent forms, or privacy constraints?_

---

## 5b. Methodology — Tool Papers

> Complete this section if the paper is a tool paper.

### Tool Description

- [ ] **Tool name and purpose**: _What does the tool do in one sentence?_

- [ ] **Target users**: _Who uses this tool and in what workflow?_

- [ ] **Implementation**: _Language, platform, key dependencies?_

- [ ] **Architecture**: _What are the main components and how do they interact?_

- [ ] **Maturity level** (tick one):
  - [ ] Research prototype (proof of concept)
  - [ ] Functional tool (tested on real projects)
  - [ ] Production-ready (deployed, maintained, used externally)

### Tool Evaluation

- [ ] **Correctness**: _How is it verified that the tool does what it claims?_

- [ ] **Performance**: _Are there efficiency or scalability requirements? How are they evaluated?_

- [ ] **Usability**: _Is a user study planned? What tasks and participants?_

- [ ] **Comparison**: _What existing tools are compared against, and on what benchmark?_

### Demo / Presentation

- [ ] **Demo scenario**: _What concrete task or example demonstrates the tool's value?_

- [ ] **Demo video**: _Is a video required by the venue? What will it show?_ (typical length: 3–5 min)

- [ ] **Live demo**: _Is a live demo planned for the presentation?_

---

## 6. Paper Story / Narrative

> Write the narrative before the paper. Reviewers accept stories, not just results.

- [ ] **One-paragraph story**: _Describe the arc: problem → gap → approach → key result → implication._

- [ ] **The "aha" moment**: _What is the one insight or result that makes this paper memorable?_

- [ ] **Null result scenario**: _What if the results are negative or mixed — is the paper still publishable? Why?_

- [ ] **Title candidates**: _Write 2–3 candidate titles._
  1. ___
  2. ___
  3. ___

---

## 7. Related Work Positioning

> Identify the 3–5 papers a reviewer will compare this work against.

For each, answer: what does that paper do, and how does this work go beyond or differ?

- [ ] **Paper 1**: _Citation_ → _How this work differs_: ___

- [ ] **Paper 2**: _Citation_ → _How this work differs_: ___

- [ ] **Paper 3**: _Citation_ → _How this work differs_: ___

- [ ] **Paper 4** _(if applicable)_: _Citation_ → _How this work differs_: ___

- [ ] **Paper 5** _(if applicable)_: _Citation_ → _How this work differs_: ___

- [ ] **Positioning statement**: _In one sentence: "Unlike prior work on X, this paper Y."_

---

## 8. Target Audience

- [ ] **Primary readers**: _Who is this paper written for?_

- [ ] **Takeaway**: _After reading, what should they be able to do or think differently?_

- [ ] **Secondary audience**: _Who else benefits (practitioners, tool builders, educators, ...)?_

---

## 9. Scope and Anticipated Limitations

> Setting scope explicitly prevents reviewer criticism of things you never claimed.

- [ ] **In scope**: _What does this work explicitly address?_

- [ ] **Out of scope**: _What is intentionally excluded and why?_

- [ ] **Threats to internal validity**: _What could bias the results within the study?_

- [ ] **Threats to external validity**: _How generalizable are the findings? What populations or contexts are excluded?_

- [ ] **Threats to construct validity**: _Do the measures actually capture what they claim to?_

- [ ] **Mitigation strategies**: _How will threats be addressed or acknowledged?_

---

## 10. Venue Fit

- [ ] **Why this venue**: _Why is this the right venue for this contribution?_

- [ ] **CFP alignment**: _Which topics from the call for papers does this work address?_

- [ ] **Format fit**: _Does the contribution type match what this venue typically accepts?_

- [ ] **Page budget sketch**: _Rough allocation of pages per section:_
  - Introduction: ___ p
  - Related Work: ___ p
  - Methodology: ___ p
  - Results: ___ p
  - Discussion: ___ p
  - Conclusion: ___ p
  - References: ___ p
  - Total: ___ / ___ allowed

---

## 11. Replication Package

> Plan the replication package before the study begins — retrofitting is harder.

### Content

- [ ] **Raw data**: _What raw data will be collected and included?_

- [ ] **Processed data**: _What derived datasets, annotations, or aggregated results?_

- [ ] **Code / scripts**: _Analysis scripts, tool source code, build scripts?_

- [ ] **Models / configs**: _Trained models, configuration files, prompts?_

- [ ] **Documentation**: _README, data dictionary, codebook, protocol?_

- [ ] **Supplementary material**: _Anything too large for the paper (full tables, interview guides, ...)?_

### Sharing Constraints

- [ ] **Privacy / ethics**: _Is any data subject to IRB restrictions or participant privacy requirements?_

- [ ] **Anonymization**: _What must be removed or pseudonymized before release?_

- [ ] **Licensing**: _What license will be applied?_ (e.g., MIT, CC BY 4.0, CC BY-NC 4.0)

- [ ] **Proprietary dependencies**: _Are there tools, datasets, or APIs that cannot be redistributed?_

### Hosting and Availability

- [ ] **Repository**: _Where will the package be hosted?_ (e.g., Zenodo, GitHub + Zenodo DOI, institutional repo)

- [ ] **Persistent identifier**: _Will a DOI be minted?_ (Zenodo provides this automatically)

- [ ] **Archive snapshot**: _Will the repository be frozen/tagged at submission?_

### Artifact Evaluation (if applicable)

- [ ] **AE track**: _Does the venue have an artifact evaluation track?_

- [ ] **Target badges** (tick all that apply):
  - [ ] Artifacts Available (publicly accessible with persistent ID)
  - [ ] Artifacts Functional (can be run, produces claimed outputs)
  - [ ] Artifacts Reusable (documented, extensible, usable beyond this paper)

- [ ] **AE README**: _Does the package include a dedicated README for evaluators with step-by-step instructions?_

- [ ] **Estimated setup time**: _How long does it take an evaluator to set up and run the artifacts?_ ___

---

## 12. Readiness Check

> Answer all questions before starting to write. If any are unclear, resolve them first.

- [ ] The core problem is stated in one precise sentence.
- [ ] The gap is distinct from "related work exists."
- [ ] The contribution is stated in one sentence with a clear novelty argument.
- [ ] All research questions are specific and answerable with the planned methodology.
- [ ] The methodology matches the research questions.
- [ ] The paper story is written as a coherent paragraph.
- [ ] The 3–5 closest related papers are identified and the differentiation is clear.
- [ ] The replication package content is planned and sharing constraints are known.
- [ ] The page budget is sketched and fits the venue's limit.
- [ ] _(Tool papers)_ The tool architecture, evaluation, and demo scenario are defined.

**Ready to write?** All boxes above checked → yes. Otherwise, resolve open items first.
