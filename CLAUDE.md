# CLAUDE.md - Academic Paper Template Configuration

Hey Claude,
this file contains configuration and guidelines for writing an academic paper using LaTeX.
Please help me adhere to these guidelines while writing the paper.
You can find lots of useful information below.
Additionally, there is some context about the specific paper I'm writing in the .claude folder.

## Paper Context

- **Type**: System and Tool Paper
- **Target Venue**: Koli Calling 2025 - International Conference on Computing Education Research
- **Format**: ACM LaTeX template (acmart class), double-column
- **Page Limit**: 10 pages + references (double-column, references excluded)
- **Review Type**: Double-anonymous
- **Submission URL**: [UPDATE when available]
- **Deadline**: [UPDATE when available]

## Paper Summary

PROMPT is an open-source course administration platform built around a phase-based course meta-model.
A course is modeled as an ordered sequence of independently operable phase instances.
Four default phases are provided: Application, Interview, Team Allocation, and Assessment.
The Assessment Phase is the pedagogically most significant: it formalizes formative feedback through
self-evaluation, peer evaluation, and instructor-defined rubric criteria at each project milestone.
The meta-model is domain-agnostic; the paper evaluates it in a computing education context (iPraktikum at TUM).
The paper is framed as a tool paper with design science contributions (the phase-based meta-model).

## Research Questions

- **RQ1**: Does the phase-based meta-model adequately capture the administrative structure of project-based courses?
- **RQ2**: How do instructors and TAs perceive the utility and usability of PROMPT for course administration?
- **RQ3**: How effectively does the plugin architecture support institution-specific and discipline-specific extensions?

## Section Structure

| Section | File | Pages |
|---|---|---|
| Introduction | chapters/01-introduction.tex | 1.5 |
| Background and Motivation | chapters/02-related-work.tex | 1.5 |
| The PROMPT Platform | chapters/03-methodology.tex | 2.5 |
| Evaluation | chapters/04-results.tex | 2.5 |
| Discussion | chapters/05-discussion.tex | 1.5 |
| Conclusion | chapters/06-conclusion.tex | 0.5 |

## Paper-Specific Guidelines

### Title

- Keep concise and descriptive
- Avoid buzzwords and overly technical jargon
- Consider keywords for discoverability

### Abstract (≤250 words typical)

- State the problem and motivation clearly
- Describe your approach/methodology briefly
- Summarize key results and findings
- Highlight main contributions and implications

### Introduction Structure

- Problem statement and motivation
- Research gaps and challenges
- Research questions/objectives
- Main contributions
- Paper organization

### Related Work Strategy

- Organize by themes/categories, not chronologically
- Position your work clearly within existing literature
- Identify specific gaps your work addresses
- Cite recent and seminal works appropriately

### Methodology Requirements

- Provide sufficient detail for replication
- Justify design choices
- Address threats to validity
- Include evaluation criteria

### Results Presentation

- Organize by research questions
- Use tables and figures effectively
- Report both positive and negative results
- Provide statistical significance where appropriate

### Discussion Structure

- Interpret results in context
- Compare with related work
- Address implications (theoretical and practical)
- Acknowledge limitations honestly

## Scientific Writing Rules

### Voice and Perspective

- **NEVER** use "our" - replace with specific nouns or passive voice
  - ❌ "Our approach shows..."
  - ✅ "The approach demonstrates..." or "This method shows..."
- **MINIMIZE** use of "we" - use sparingly and only when absolutely necessary
  - ❌ "We implemented a solution..."
  - ✅ "The authors implemented..." or "Implementation involved..."
- **ALWAYS** use active voice when possible
  - ❌ "The system was designed by the team"
  - ✅ "The team designed the system"

### Prohibited Words and Phrases

- **NEVER** use "comprehensive" - use specific descriptors instead
  - ❌ "comprehensive analysis"
  - ✅ "detailed analysis" or "thorough examination"
- Avoid vague qualifiers: "very", "quite", "rather", "fairly"
- Avoid subjective language: "obviously", "clearly", "naturally"
- Minimize hedge words: "seems", "appears", "might", "perhaps"

### Preferred Language Patterns

- Use specific, concrete terms over general ones
- Replace "investigate" with "examine", "analyze", or "study"
- Replace "utilize" with "use"
- Replace "facilitate" with "enable" or "support"
- Use present tense for general truths, past tense for specific actions

## Custom LaTeX Features

### Finding Boxes

Use `\\begin{findingBox}` to document key observations:

```latex
\\begin{findingBox}
Students preferred syntax highlighting over advanced debugging features (95.6% vs 67.2%).
\\end{findingBox}
```

### Recommendation Boxes

Use `\\begin{recommendationBox}` for actionable advice:

```latex
\\begin{recommendationBox}
Educators should prioritize basic IDE features before implementing advanced functionality.
\\end{recommendationBox}
```

### Fulfillment Boxes

Use `\\begin{fulfillment}` to document requirement satisfaction:

```latex
\\begin{fulfillment}
The architecture satisfies scalability requirements through Kubernetes orchestration.
\\end{fulfillment}
```

### Writing Support Commands

- `\\missing{text}` - Yellow highlight for missing content
- `\\feedback{text}` - Green highlight for feedback requests
- `\\authorassignment{name}` - Cyan highlight for author assignments
- `\\TODO` - Red TODO marker

### Table Formatting Commands

- `\\cmark` - Green checkmark
- `\\xmark` - Red cross mark
- `\\strong`, `\\moderate`, `\\weak`, `\\limited`, `\\nosupport` - Colored strength indicators

## Latex Code Style Instructions

Please make sure to start every sentence in a new latex line to facilitate diffs and reviews.

## Build and Compilation

### Primary Build Command

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error paper.tex
```

### Clean Build Files

```bash
latexmk -c paper.tex
```

### Check for Compilation Issues

```bash
pdflatex -interaction=nonstopmode paper.tex
```


## Review Checklist

### Content Quality

- [ ] All research questions clearly addressed
- [ ] Methodology described with sufficient detail
- [ ] Results presented objectively with evidence
- [ ] Discussion connects findings to broader context
- [ ] Limitations acknowledged appropriately
- [ ] Contributions clearly stated and significant

### Writing Quality

- [ ] No use of "our" anywhere in text
- [ ] Minimal use of "we" (only where essential)
- [ ] Active voice throughout
- [ ] No use of "comprehensive" or other prohibited words
- [ ] Specific, concrete language used
- [ ] Clear transitions between sections
- [ ] Consistent terminology throughout

### Format and Structure

- [ ] ACM template used correctly
- [ ] Page limit respected
- [ ] All sections properly organized
- [ ] Figures and tables properly formatted and referenced
- [ ] Citations complete and consistent
- [ ] Abstract within word limit

### Technical Quality

- [ ] LaTeX compiles without errors or warnings
- [ ] All references resolve correctly
- [ ] All custom commands work properly
- [ ] No missing `\\missing{}` items remain
- [ ] All TODO items addressed

## Citation Guidelines

### BibTeX Usage

- Use `\\cite{}` for parenthetical citations: (Author, 2023)
- Use `\\citet{}` for narrative citations: Author (2023) found that...
- Use `\\citeauthor{}` for author names only: Author's approach...

### Reference Management

- Store all references in `references.bib`
- Use consistent citation keys (author_year_keyword)
- Include DOIs and URLs where available
- Ensure all citations are complete and accurate

## Anonymization Guidelines

### For Anonymous Submission

Uncomment and customize the anonymization commands in `paper.tex`:

- `\\university` instead of specific university names
- `\\city` instead of specific city names
- `\\group` instead of specific research group names
- `\\githubRepo` for repository placeholders

### Remove Identifying Information

- Author names and affiliations
- Acknowledgments mentioning specific people/institutions
- URLs to personal/institutional repositories
- Self-citations that could reveal identity

## Common Commands

### Git Workflow

```bash
# Check status
git status

# Stage changes
git add paper.tex chapters/

# Commit with descriptive message
git commit -m "Update [section]: [brief description]"
```

### Word Count

```bash
# Count words in main sections (excluding references)
texcount -inc paper.tex
```

### Spell Check

```bash
# Run spell checker
aspell -c paper.tex
```

## Final Submission Checklist

- [ ] All content complete and proofread
- [ ] No `\\missing{}` or `\\TODO` items remain
- [ ] Bibliography complete and formatted correctly
- [ ] Figures and tables have proper captions and labels
- [ ] Paper compiles without errors
- [ ] Page/word limits respected
- [ ] Anonymization requirements met (if applicable)
- [ ] All co-authors have reviewed final version
- [ ] Submission guidelines followed

## Notes for Customization

When starting a new paper:

1. Update the "Paper Context" section with your specific details
2. Customize anonymization commands for your institutions
3. Add your specific acronyms to the acronym definitions
4. Update author information in `paper.tex`
5. Modify the chapter structure if needed
6. Add your bibliography file and update the reference in `paper.tex`
