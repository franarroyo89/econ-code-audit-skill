# Audit checks

Apply only relevant checks. Distinguish intended definitions, implementation, and identifying assumptions.

## Data and samples

- Trace provenance, vintage, units, coverage, revisions, country classifications, and access conditions. Preserve raw inputs.
- Establish observation level and intended keys. Test uniqueness on the appropriate merge side, cardinality, unmatched observations, and duplicate unit-period records. A many-to-many merge is not automatically wrong; establish intended cardinality and aggregation.
- Record N and unit identities before/after filters, merges, collapses, and estimator-specific exclusions. Distinguish intended restrictions from accidental common-sample restrictions.
- Examine missing-value semantics, sentinel codes, infinities, coercion, implicit deletion, and zero filling. In Stata, numeric missings exceed finite values; in pandas, groupby and merge missing-key behavior can affect samples. Check actual language/version behavior.
- Check reshape, aggregation levels, weights, denominators, and normalization. Check whether weighted aggregates use intended time-varying or fixed weights and handle missing constituents consistently.

## Variables and timing

- Trace outcome and regressor construction: levels/logs, differences/growth rates, percentage points/percent, currency conversions, deflation, index rebasing, annualization, seasonal adjustment.
- Verify calendar lags/leads with panel gaps, sorting, duplicate periods, cross-unit boundaries, horizons, rolling windows, and release dates. For forecasting, check leakage, training-only transformations, and real-time information sets.
- For local projections, match the baseline, cumulative definition, horizon-specific samples, lag/lead controls, and response normalization to the intended equation.
- For VAR/SVAR and simulations, check variable ordering, identification/normalization, elasticity/sign conventions, horizon indexing, stability, random streams, and simulated truth versus reported targets.

## Estimation and inference

- Match outcome, regressors, weights, intercepts, fixed effects, interactions, covariance estimators, clustering, and restrictions to the intended specification.
- Check rank/collinearity and identifying variation after absorption. A common time series in a single-group panel may be absorbed by year effects; interacted exposure may retain variation. Establish the actual design matrix.
- Examine cluster count, imbalance, leverage, dependence, and appropriate finite-sample inference. Do not use a universal 50-cluster threshold.
- For DiD, inspect treatment timing, comparison units, anticipation, heterogeneity, and estimator assumptions. Non-rejection of pre-trends is not proof of parallel trends.
- For IV, inspect first-stage specification, exclusion/independence arguments, and strength diagnostics appropriate to the design and covariance structure. An F-statistic alone does not establish identification.
- Identify post-treatment controls, selection, look-ahead, and causal overclaiming as research-design concerns, not necessarily coding bugs.
- Inspect uncertainty calculations, bootstrap resampling unit, repeated tests, model selection, and seed/stream handling. Avoid resetting an identical seed inside a loop when distinct draws are intended.

## Outputs and alignment

- Map tables/figures/headline numbers to generating scripts, estimator objects, specification labels, sample definitions, scaling, and rounding. Check stale or overwritten results and manually edited outputs.
- Match manuscript equations, samples, periods, variables, fixed effects, standard errors, and quantitative statements. “Not located” means only not located within reviewed coverage.
- Separate reproducible computation from defensible interpretation. Do not demand a robustness exercise merely because it appears on a checklist.

## Package reproducibility

- Check documented entry point and run order, portable path configuration, pinned environments or equivalent, software and package versions, licenses/access instructions, runtime, hardware, and outputs-to-scripts mapping.
- Test regeneration in a clean copy without relying on undeclared local files, cached intermediates, or session state. For notebooks, execute in kernel order from a clean session when feasible.
- Record missing data/software as blockers without inventing results. Restricted data can be appropriately documented rather than publicly bundled.
- Use a coherent RNG strategy appropriate to stochastic procedures; deterministic scripts need no seed. A lockfile alone does not prove the environment runs.
- Assess functional portability rather than forbidding all absolute paths, spaces, or particular folder names. Formatting and loop-index preferences are not replication failures.
- Verify manually entered manuscript numbers against generated values; recommend automation in proportion to error risk, not as an automatic major finding.
