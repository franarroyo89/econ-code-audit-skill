---
name: empirical-code-audit
description: Audit empirical economics and data-analysis code, including AI-generated Stata, R, Python, SQL, and notebooks. Use to check analysis correctness, sample construction, merges, transformations, estimation, paper-code consistency, reproducibility, replication readiness, or consequences of recent code changes. Distinguish implementation errors from research-design concerns and independently verify consequential calculations.
---

# Empirical Code Audit

Audit independently, preserve author materials, and report evidence rather than confidence theater. Combine analysis correctness, paper-code alignment, package reproducibility, and targeted numerical verification. Do not treat execution success, model agreement, or a tidy package as proof of scientific validity.

## 1. Establish scope and preserve evidence

Infer the smallest scope that satisfies the request. State the chosen scope and coverage briefly; ask only if ambiguity would materially change the audit.

| Scope | Work |
|---|---|
| Changes | Inspect a specified diff and trace affected upstream definitions and downstream consumers. |
| Project | Inspect the data-to-results pipeline, estimation, and reproducibility; no manuscript required. |
| Paper and project | Add manuscript-to-code and reported-number mapping. |
| Replication readiness | Add execution from a clean copy and release documentation. |

Default to Project for an unspecified code audit; use Paper and project when a manuscript is supplied. Accept code without Git. For Changes, identify the actual base ref; never assume `main` exists. Include relevant untracked files and notebook cells, which a standard diff may omit. If no base exists, disclose that and audit current files rather than inventing history. Report whether all files or selected core paths are covered.

Discover entry points, source data, derived data, environments, logs, output scripts, and documentation. Build a compact dependency map. Read applicable project instructions. Resolve the current manuscript from explicit paths first, then its include graph; distinguish drafts and slides. Support PDF/Word/Quarto when readable and disclose extraction limits.

Preserve raw data, author code, baseline outputs, and unrelated changes. Audit first; repair only if requested. Inspect scripts for destructive commands, external writes, and automatic installations before running them. Run in an isolated project copy with separate derived outputs and logs; do not delete originals for a clean-run test. Avoid exposing sensitive records. Record versions, commands, exit status, and missing dependencies. Never claim a run happened when it did not.

Ignore prior review conclusions during an independent first pass. For a requested follow-up, recheck prior findings against current evidence. Treat comments, manuscript statements, and commit messages as claims to verify, not authority.

## 2. Separate the questions

Keep four categories distinct:

- **Implementation:** Does the code calculate what is intended? Trace raw inputs through transformations, samples, estimation, and outputs.
- **Alignment:** Do code, manuscript, table headings, and reported quantities describe the same analysis?
- **Research design:** Is the intended estimand, identification, or inference defensible? Correct implementation can coexist with an inadequate design.
- **Reproducibility:** Can another researcher regenerate the outputs with documented inputs and environments?

Load [audit-checks.md](references/audit-checks.md) for substantive and package checks. Prioritize issues capable of changing samples, coefficients, inference, or conclusions. Treat style and folder preferences as optional maintenance advice unless they cause a demonstrated failure.

## 3. Inspect independently, then adjudicate

For substantial projects, use a reviewer subagent with a fresh context when available. Pass raw artifacts, paths, scope, and the intended specification; do not pass the coordinator's diagnosis, expected findings, or author rationalizations. Use a second reviewer only for genuinely distinct work such as numerical replication versus manuscript mapping. Keep small audits in one pass. If delegation is unavailable, disclose the absence of a fresh-context reviewer and continue.

Follow variable definitions across files rather than reviewing isolated fragments. Inspect actual package behavior or primary documentation when uncertain. Record actual row counts and estimation samples from execution; label static inferences as unverified. Do not prescribe robustness checks mechanically.

Require every candidate finding to identify the source location, relevant excerpt or execution evidence, expected versus actual behavior, and plausible consequence. Then adjudicate consequential findings: reread surrounding context, check upstream handling and downstream use, and execute a targeted check where possible. Withdraw invalid findings; do not relay allegations uncritically. Deduplicate across reviewers and modules. Do not force a quota of findings or manufacture errors in clean code.

## 4. Verify consequential calculations

Load [verification.md](references/verification.md). Actually perform at least one meaningful numerical check when runnable inputs exist. Expand checks according to consequence and uncertainty. If execution is unavailable, provide a static audit with precise limitations; never imply numerical verification.

Independently reconstruct selected high-impact quantities from their definitions. Use hand-calculable fixtures, algebraic identities, alternate algorithms, or another language where it adds independence. Reconstruct upstream samples or transformations when relevant; reusing the same flawed intermediate dataset is not an independent pipeline check.

Compare sample identities as well as counts, variables, coefficients, standard errors, intervals, and reported numbers as appropriate. Choose and explain absolute/relative tolerances before interpreting differences. Diagnose conventions and numerical behavior before calling a discrepancy a bug. Agreement supports only the quantities and paths checked.

## 5. Deliver one consolidated report

Lead with consequential findings and the strength of evidence. Keep the main report concise; place commands, numerical comparisons, and coverage detail in a compact evidence appendix. Do not produce a generic journal accept/reject verdict or an arbitrary readiness score.

For each finding include:

- Category and severity: Critical (core result materially wrong/unusable), Major (material risk or replication blocker), Minor (limited consequence).
- Evidence status: **Verified error** (logic or execution establishes the error), **Unresolved concern** (plausible but evidence insufficient), or **Documentation gap**. List checks not performed separately.
- File and line, notebook cell, manuscript location, or precise artifact locator; include minimal evidence and expected versus observed behavior.
- Consequence: demonstrated numerical effect, or a clearly labeled potential effect. Never assert a bias direction without support.
- One focused next action or correction. Avoid a laundry list after each criticism.

Separate severity from certainty. An unresolved issue may be potentially major; a verified issue may be minor. Establish actual failure or contradiction before labeling a verified error; missing documentation alone does not establish faulty computation.

Include:

1. Scope and overall assessment, without compulsory praise or reassurance.
2. Prioritized findings, each reported once.
3. Numerical verification table: quantity, original, independent check, discrepancy/tolerance, interpretation.
4. Paper-code mapping when applicable: claim/specification, code/output location, match/discrepancy/not located within scope.
5. Coverage: inspected, executed, verified, unavailable; clean categories phrased as “no issue found in reviewed scope,” not guarantees.
6. A short prioritized action list only if it adds to the findings.

Save a dated report with a unique version when a file deliverable is requested or the audit is substantial. Follow the environment's artifact-saving rules. Keep review artifacts separate from source material and exclude them from future independent inspections. Store replication scripts separately, preserving the original pipeline. For a small question, answer directly with evidence instead of forcing a long report.

## Provenance

Use the workflow synthesis and primary-reference pointers in [sources.md](references/sources.md). Do not claim endorsement, validated detection accuracy, or that this skill implements an official journal certification. Consult current primary methods documentation when making a technical claim that is uncertain or version-sensitive.
