# Academic Paper Template

A LaTeX template for ACM-format academic papers, designed to be used together with Claude Code.
It includes custom writing environments, a structured conceptualization workflow, and writing guidelines enforced via `CLAUDE.md`.

---

## How to Use This Template

Work through the phases below in order.
**Do not start writing before completing Phase 2** — the conceptualization gates everything that follows.

---

### Phase 1: Set Up

1. Copy or clone this repository for your new paper and give it a descriptive name.
2. Verify the template compiles:
   ```bash
   latexmk -pdf -interaction=nonstopmode paper.tex
   ```
3. Update the **Paper Context** section at the top of `CLAUDE.md` with your venue, deadline, page limit, and review type.

---

### Phase 2: Configure the Venue Context

Fill in the three context files in `.claude/` before doing anything else.
Claude reads these files throughout the project to tailor writing advice and flag weaknesses.

| File | Purpose |
|---|---|
| `.claude/concept.md` | Paper conceptualization checklist — the core planning document |
| `.claude/call-for-paper.md` | Venue call for papers — scope, topics, formatting requirements |
| `.claude/review-criteria.md` | Review criteria — what reviewers will evaluate |

**Tip:** Paste the call for papers into `call-for-paper.md` and ask Claude to help extract the key constraints and update `paper.tex` accordingly (title format, CCS concepts, keywords, page setup).

---

### Phase 3: Conceptualize the Paper

Open `.claude/concept.md` and work through all sections:

1. **Paper Type** — empirical study, tool paper, replication, etc.
2. **Problem** — specific problem, who is affected, why now
3. **Gap** — what exists, where it falls short, the precise gap
4. **Core Contribution** — one-sentence contribution with novelty argument
5. **Research Questions** — specific, answerable RQs with planned methodology
6. **Methodology** — research method, data, evaluation, ethics *(tool papers: also complete §5b)*
7. **Paper Story** — one-paragraph narrative arc before writing anything
8. **Related Work** — 3–5 closest papers and explicit differentiation
9. **Target Audience** — who reads this and what they take away
10. **Scope & Limitations** — what is in and out of scope; anticipated threats
11. **Venue Fit** — why this venue; rough page budget per section
12. **Replication Package** — what is shared, where, under what license; AE badge goals

**Complete the readiness check at the end of `concept.md` before moving to Phase 4.**

Claude can actively help during this phase — ask it to challenge your gap statement, stress-test your RQs, or draft the paper story paragraph.

---

### Phase 4: Set Up the Paper

Once conceptualization is complete:

1. Update `paper.tex`:
   - Title, authors, affiliations, ORCID links
   - Abstract (use the `\missing{}` prompts as a guide)
   - CCS concepts (from [https://dl.acm.org/ccs](https://dl.acm.org/ccs))
   - Keywords

2. Configure anonymization if the venue uses blind review:
   - Use `\universityname`, `\cityname`, `\groupname` placeholders
   - Switch the document class to `\documentclass[sigconf,anonymous,review]{acmart}`

3. Adjust the chapter structure in `paper.tex` if your paper needs different sections (e.g., tool papers may rename or reorder sections).

---

### Phase 5: Write

Work chapter by chapter. Each chapter file contains `% Concept §X` comments that link back to the relevant section of `concept.md`.

- Use `\missing{...}` to mark content not yet written
- Use `\TODO` to mark decisions not yet made
- Use `\feedback{...}` to request co-author review
- Use `\authorassignment{name}` to assign sections to co-authors
- Add references to `references.bib` as you write (use `author_year_keyword` keys)
- Place figures in `figures/`
- Build regularly to catch LaTeX errors early:
  ```bash
  latexmk -pdf paper.tex
  ```

Ask Claude to help write, review, or restructure individual sections.
Claude will enforce the writing rules from `CLAUDE.md` — no "our", no "comprehensive", active voice, sentence-per-line LaTeX style.

---

### Phase 6: Review and Refine

When a draft is complete, run through the review checklist in `CLAUDE.md`:

- **Content**: All RQs answered, methodology sufficient for replication, results objective
- **Writing**: No prohibited words, active voice, concrete language, consistent terminology
- **Format**: ACM template correct, page limit respected, figures/tables properly captioned
- **Technical**: Compiles without errors, all references resolve, no `\missing{}` or `\TODO` remaining

Check word count:
```bash
texcount -inc paper.tex
```

---

### Phase 7: Prepare for Submission

1. Resolve all `\missing{}` and `\TODO` markers.
2. Finalize the **Data Availability** section in `paper.tex` with the replication package URL or Zenodo DOI.
3. Upload the replication package and verify it is complete (see concept.md §11).
4. If submitting to an Artifact Evaluation track, prepare the AE README.
5. Switch the document class to the appropriate submission mode:
   ```latex
   % Double-blind review:
   \documentclass[sigconf,anonymous,review]{acmart}
   % Camera-ready:
   \documentclass[sigconf,screen]{acmart}
   ```
6. Do a final build, check page count, and review the PDF before uploading.

---

## File Structure

```
paper-template/
├── paper.tex                  # Main document (preamble, structure, custom commands)
├── chapters/                  # One file per chapter
│   ├── 01-introduction.tex
│   ├── 02-related-work.tex
│   ├── 03-methodology.tex     # Includes commented-out tool paper section
│   ├── 04-results.tex
│   ├── 05-discussion.tex
│   └── 06-conclusion.tex
├── figures/                   # Figures (PDF, PNG, SVG)
├── references.bib             # BibTeX bibliography
├── .claude/                   # Claude context files — fill in before writing
│   ├── concept.md             # Paper conceptualization checklist (start here)
│   ├── call-for-paper.md      # Venue call for papers
│   └── review-criteria.md     # Venue review criteria
├── CLAUDE.md                  # Writing rules and guidelines for Claude
├── acmart.cls                 # ACM document class
├── acmart-tagged.cls
└── ACM-Reference-Format.bst   # ACM bibliography style
```

---

## Custom LaTeX Features

### Environments

**Finding Box** — for key observations from the data:
```latex
\begin{findingBox}
Students preferred syntax highlighting over advanced debugging features (95.6% vs 67.2%).
\end{findingBox}
```

**Recommendation Box** — for actionable recommendations:
```latex
\begin{recommendationBox}
Educators should prioritize basic IDE features before implementing advanced functionality.
\end{recommendationBox}
```

**Fulfillment Box** — for documenting requirement satisfaction:
```latex
\begin{fulfillment}
The architecture satisfies scalability requirements through Kubernetes orchestration.
\end{fulfillment}
```

### Writing Support Commands

| Command | Color | Purpose |
|---|---|---|
| `\missing{text}` | Yellow | Content not yet written |
| `\feedback{text}` | Green | Request co-author review |
| `\authorassignment{name}` | Cyan | Assign section to author |
| `\TODO` | Red | Decision or action pending |

### Table Formatting

| Command | Output |
|---|---|
| `\cmark` | Green checkmark |
| `\xmark` | Red cross |
| `\strong` | **Strong** (green) |
| `\moderate` | **Moderate** (orange) |
| `\weak` | **Weak** (red) |
| `\limited` | **Limited** (grey) |
| `\nosupport` | **No Support** (red) |

### Citation Commands

| Command | Use |
|---|---|
| `\cite{key}` | Parenthetical: (Author, 2023) |
| `\citet{key}` | Narrative: Author (2023) found that... |
| `\citeauthor{key}` | Author name only |

---

## Build Commands

```bash
# Compile to PDF
latexmk -pdf -interaction=nonstopmode paper.tex

# Clean auxiliary files
latexmk -c paper.tex

# Word count
texcount -inc paper.tex
```

## CI / Artifact Download

A GitHub Actions workflow (`.github/workflows/build.yml`) automatically compiles the paper on every push to `main` and on every pull request.
The compiled PDF is uploaded as a build artifact and can be downloaded from the **Actions** tab of the repository for 30 days.

---

## License

This template is provided as-is for academic use. The ACM class files (`acmart.cls`, `acmart-tagged.cls`, `ACM-Reference-Format.bst`) retain their original ACM licenses.
