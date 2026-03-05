---
paths:
  - "Code/**/*.do"
  - "Code/**/*.py"
  - "Code/**/*.m"
---

# Multi-Language Conventions

This project uses Stata, Python, and Matlab for analysis. This file documents conventions for each language.

---

## Stata Conventions

### File Organization
- One `.do` file per analysis task
- Master `.do` file in `Code/baseline/` that runs all scripts in order
- Use relative paths from repo root

### Coding Standards
- Set seed at top: `set seed 20260305`
- Use `clear all` at start of each script
- Comment every regression specification
- Save results to `Tables/` and `Figures/`

### Common Pitfalls
- [To be filled in as discovered]

---

## Python Conventions

### File Organization
- One `.py` file per analysis task
- Use `requirements.txt` for dependencies
- Use relative paths from repo root

### Coding Standards
- Set seed at top: `np.random.seed(20260305)`
- Use `pathlib` for cross-platform paths
- Type hints for function signatures
- Save results to `Tables/` and `Figures/`

### Common Pitfalls
- [To be filled in as discovered]

---

## Matlab Conventions

### File Organization
- One `.m` file per analysis task
- Master script in `Code/baseline/` that runs all scripts in order
- Use relative paths from repo root

### Coding Standards
- Set seed at top: `rng(20260305)`
- Comment every major operation
- Save results to `Tables/` and `Figures/`

### Common Pitfalls
- [To be filled in as discovered]

---

## Cross-Language Standards

- **Tolerance thresholds:** Point estimates 1e-6, SEs 1e-4
- **Figure format:** PNG or PDF, 300 DPI, transparent background
- **Table format:** LaTeX-ready `.tex` files
- **Naming:** Descriptive names (e.g., `baseline_regression.do`, `robustness_check_1.py`)
