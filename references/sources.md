# Workflow provenance and primary references

Use this original synthesis of approaches inspected on 2026-11-05; do not present it as verbatim upstream code or an endorsement.

- Claes Bäckman, AI Research Feedback: https://github.com/claesbackman/AI-research-feedback
  - Skills/audit-analysis/SKILL.md: fresh-context diff audit, sample/merge/variable/estimation checks, anchored findings, confirmed versus suspected evidence.
  - Skills/review-paper-code/SKILL.md: project discovery, manuscript-code mapping, bounded coverage, reproducibility inspection.
- Lee Crawfurd, Claude Skills: https://github.com/lcrawfurd/claude-skills
  - code-review.md: package organization, master execution, data management, dependencies, documentation, output reproducibility.
  - referee2.md: read/run without modifying author code, targeted cross-language replication, econometric implementation checks. Credits Scott Cunningham's MixtapeTools: https://github.com/scunning1975/MixtapeTools

Consult primary standards when needed:

- Gentzkow and Shapiro, Code and Data for the Social Sciences: https://web.stanford.edu/~gentzkow/research/CodeAndData.pdf
- World Bank DIME Data Handbook, coding: https://worldbank.github.io/dime-data-handbook/coding.html
- Julian Reif, Stata Coding Guide: https://julianreif.com/guide/
- AEA Data Editor: https://aeadataeditor.github.io/
- Social Science Data Editors README template: https://social-science-data-editors.github.io/template_README/
- Project TIER: https://www.projecttier.org/

Deliberate revisions: adjudicate findings after the independent pass; separate implementation, design, alignment, and reproducibility; require targeted execution where feasible; calibrate tolerances; reject universal cluster-count cutoffs; avoid arbitrary readiness scores and automatic severity based on formatting. Do not infer accuracy from author credentials or adoption counts.
