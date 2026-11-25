# Numerical verification protocol

1. Select a consequential quantity and write its intended definition before implementing the check. Choose checks that can detect actual errors, not merely restate production code.
2. Preserve baseline code/data/output. Record the entry point, environment, input identities, execution status, and audit copy location. Inspect external writes and deletion behavior first.
3. Choose an independent route: a hand-worked small dataset; an algebraic identity; a closed-form calculation; a different algorithm/library; or a second language derived from the specification. Do not translate production lines mechanically.
4. Verify upstream inputs to the selected calculation. For sample construction, compare keys and exclusions, not N alone. For time operations, use gaps and unit boundaries. For merges, use controlled duplicate/unmatched keys. Include a valid control case when testing suspicious behavior.
5. For regression comparisons, align samples, weights, intercepts, fixed effects, singleton handling, absorbed degrees of freedom, covariance estimators, and finite-sample corrections. Different conventions can legitimately change output.
6. Specify scale-appropriate absolute and relative tolerances. Account for conditioning, convergence, stochastic Monte Carlo error, and published rounding. Do not require six decimals universally or bit-identical PDFs.
7. Run the original and independent calculation where feasible. Record compared quantities, discrepancies, and interpretation. Trace mismatches before declaring which implementation is wrong. If neither is established, report unresolved.
8. For AI-generated work, prioritize independent reconstruction of data transformations and the central specification. A fresh context or different language reduces some shared mistakes but establishes no statistical independence of errors.
9. State the limit: selected numerical agreement does not verify every pipeline branch, identification assumption, or scientific conclusion. If inputs or tools are absent, label the check not performed and give the exact blocker.
