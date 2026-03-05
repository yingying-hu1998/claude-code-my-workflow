---
paths:
  - "Paper/**/*.tex"
  - "Code/**"
---

# Task Completion Verification Protocol

**At the end of EVERY task, Claude MUST verify the output works correctly.** This is non-negotiable.

## For LaTeX Papers:
1. Compile with latexmk: `latexmk -xelatex -interaction=nonstopmode paper.tex`
2. Check for compilation errors and undefined citations
3. Check for overfull hbox warnings (> 10pt in body text)
4. Open the PDF to verify figures/tables render correctly
5. Verify all `\ref{}` and `\cite{}` resolve correctly
6. Report verification results

## For Analysis Scripts (R/Stata/Python/Matlab):
1. Run the script: `Rscript Code/baseline/script.R` (or equivalent)
2. Verify output files (tables, figures) were created with non-zero size
3. Spot-check estimates for reasonable magnitude
4. Verify tolerance matching if replicating published results
5. Check that figures saved to `Figures/` and tables to `Tables/`

## For Figures:
1. Verify figure files exist in `Figures/` directory
2. Check file format (PDF or PNG, 300 DPI minimum)
3. Open figure to confirm it displays correctly
4. Verify transparent background if specified
5. Check that LaTeX can find and include the figure

## For Tables:
1. Verify table files exist in `Tables/` directory
2. Check format (LaTeX-ready `.tex` files)
3. Verify table compiles in paper without errors
4. Check alignment and formatting

## Common Pitfalls:
- **Absolute paths**: Always use relative paths from repo root
- **Missing files**: Verify all referenced figures/tables exist before compiling
- **Undefined citations**: Check Bibliography_base.bib has all entries
- **Assuming success**: Always verify output files exist AND contain correct content

## Verification Checklist:
```
[ ] Output file created successfully
[ ] No compilation/execution errors
[ ] Figures/tables display correctly
[ ] All references resolve (citations, figures, tables)
[ ] Opened PDF/output to confirm visual appearance
[ ] Reported results to user
```
