# Workflow Quick Reference

**Model:** Contractor (you direct, Claude orchestrates)

---

## The Loop

```
Your instruction
    ↓
[PLAN] (if multi-file or unclear) → Show plan → Your approval
    ↓
[EXECUTE] Implement, verify, done
    ↓
[REPORT] Summary + what's ready
    ↓
Repeat
```

---

## I Ask You When

- **Design forks:** "Option A (fast) vs. Option B (robust). Which?"
- **Code ambiguity:** "Spec unclear on X. Assume Y?"
- **Replication edge case:** "Just missed tolerance. Investigate?"
- **Scope question:** "Also refactor Y while here, or focus on X?"

---

## I Just Execute When

- Code fix is obvious (bug, pattern application)
- Verification (tolerance checks, tests, compilation)
- Documentation (logs, commits)
- Plotting (per established standards)
- Deployment (after you approve, I ship automatically)

---

## Quality Gates (No Exceptions)

| Score | Action |
|-------|--------|
| >= 80 | Ready to commit |
| < 80  | Fix blocking issues |

---

## Non-Negotiables

- **Compilation:** latexmk -xelatex for all LaTeX papers
- **Path convention:** Relative paths from repo root (e.g., `Figures/fig1.pdf`)
- **Seed convention:** `set.seed(20260305)` once at top of all stochastic scripts
- **Figure standards:** Transparent background, 300 DPI, institutional colors
- **Color palette:** [Customize: Primary #012169, Gold #f2a900, Gray #525252]
- **Tolerance thresholds:** Point estimates 1e-6, SEs 1e-4, p-values same significance
- **Replication:** Strict tolerance matching (flag near-misses, investigate)

---

## Preferences

**Visual:** Figures with transparent bg, institutional colors, minimal theme
**Reporting:** Concise bullets for verification; detailed prose for reviews
**Session logs:** Always (post-plan, incremental, end-of-session)
**Replication:** Strict — flag any tolerance miss, investigate root cause
**Paper structure:** Intro → Model → Empirics → Results → Robustness → Conclusion
**Code organization:** Baseline replication first, then extensions
**Multi-language:** Stata/Python/Matlab (see `.claude/rules/multi-language-conventions.md`)

---

## Exploration Mode

For experimental work, use the **Fast-Track** workflow:
- Work in `explorations/` folder
- 60/100 quality threshold (vs. 80/100 for production)
- No plan needed — just a research value check (2 min)
- See `.claude/rules/exploration-fast-track.md`

---

## Next Step

You provide task → I plan (if needed) → Your approval → Execute → Done.
