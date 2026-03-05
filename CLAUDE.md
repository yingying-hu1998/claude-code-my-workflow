# CLAUDE.MD -- Academic Project Development with Claude Code

<!-- HOW TO USE: Replace [BRACKETED PLACEHOLDERS] with your project info.
     Customize Beamer environments and CSS classes for your theme.
     Keep this file under ~150 lines — Claude loads it every session.
     See the guide at docs/workflow-guide.html for full documentation. -->

**Project:** Econ Paper Workflow Template
**Institution:** ZZX
**Branch:** main

---

## Core Principles

- **Plan first** -- enter plan mode before non-trivial tasks; save plans to `quality_reports/plans/`
- **Verify after** -- compile/render and confirm output at the end of every task
- **Single source of truth** -- LaTeX `.tex` is authoritative; figures/tables/code derive from it
- **Quality gates** -- nothing ships below 80/100
- **[LEARN] tags** -- when corrected, save `[LEARN:category] wrong → right` to MEMORY.md

---

## Folder Structure

```
[YOUR-PROJECT]/
├── CLAUDE.MD                    # This file
├── .claude/                     # Rules, skills, agents, hooks
├── Bibliography_base.bib        # Centralized bibliography
├── Figures/                     # Generated figures
├── Tables/                      # Generated tables
├── Preambles/header.tex         # LaTeX headers
├── Paper/                       # Main paper.tex + appendix.tex
├── Code/                        # Analysis scripts
│   ├── baseline/                # Original replication
│   ├── extensions/              # Your extensions
│   └── robustness/              # Robustness checks
├── docs/                        # Documentation
├── quality_reports/             # Plans, session logs, merge reports
├── explorations/                # Research sandbox (see rules)
├── templates/                   # Session log, quality report templates
└── master_supporting_docs/      # Papers and existing materials
```

---

## Commands

```bash
# LaTeX paper compilation (latexmk)
latexmk -xelatex -interaction=nonstopmode paper.tex

# Generate figures
Rscript Code/baseline/generate_figures.R

# Generate tables
Rscript Code/baseline/generate_tables.R

# Run replication
Rscript Code/baseline/replicate_baseline.R

# Quality score
python Code/quality_score.py paper.tex
```

---

## Quality Thresholds

| Score | Gate | Meaning |
|-------|------|---------|
| 80 | Commit | Good enough to save |
| 90 | PR | Ready for deployment |
| 95 | Excellence | Aspirational |

---

## Skills Quick Reference

| Command | What It Does |
|---------|-------------|
| `/compile-latex [file]` | Compile LaTeX with latexmk -xelatex |
| `/proofread [file]` | Grammar/typo/overflow review |
| `/review-paper [file]` | Manuscript review |
| `/validate-bib` | Cross-reference citations |
| `/commit [msg]` | Stage, commit, PR, merge |
| `/lit-review [topic]` | Literature search + synthesis |
| `/research-ideation [topic]` | Research questions + strategies |
| `/interview-me [topic]` | Interactive research interview |
| `/review-r [file]` | R code quality review |
| `/data-analysis [dataset]` | End-to-end analysis workflow |
| `/learn [skill-name]` | Extract discovery into persistent skill |
| `/context-status` | Show session health + context usage |
| `/deep-audit` | Repository-wide consistency audit |

---

<!-- CUSTOMIZE: Replace the example entries below with your own
     Beamer environments and Quarto CSS classes. These are examples
     from the original project — delete them and add yours. -->

## LaTeX Custom Environments

| Environment       | Effect        | Use Case       |
|-------------------|---------------|----------------|
| `[your-env]`      | [Description] | [When to use]  |

<!-- Example entries (customize for your paper template):
| `\begin{theorem}` | Numbered theorem | Formal results |
| `\begin{proof}` | Proof environment | Derivations |
| `\begin{assumption}` | Numbered assumption | Model assumptions |
-->

---

## Current Project State

| Paper | Main File | Key Sections |
|-------|-----------|-------------|
| [Paper Name] | paper.tex | Introduction, Model, Empirics, Results, Robustness, Conclusion |
| [Appendix] | appendix.tex | Additional derivations, robustness tables |

