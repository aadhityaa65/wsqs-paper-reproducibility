# Aggregate study evaluation results

This directory provides selected aggregate evaluation tables associated with the study. It contains no respondent identifiers, individual prediction records or household survey microdata.

- `benchmark_split_level.csv` and `benchmark_summary.csv` summarize seven learner comparisons across ten partitions.
- `block_models.csv`, `block_shapley.csv` and `block_reference_comparison.csv` describe predictor-block prediction performance and allocation.
- `cross_domain_models.csv` and `cross_domain_reference_comparison.csv` summarize target-domain predictor-exclusion checks.
- `sensitivity_models.csv` reports outcome and feature sensitivities. CORE-7A uses 25 service-support and context (SC) predictors; CORE-7B uses 33 service-support, context and priorities (SCP) predictors, with its original held-out RMSE and selected CatBoost iterations.

See [`REPRODUCIBILITY_SCOPE.md`](../../REPRODUCIBILITY_SCOPE.md) for the scope of the underlying computations. Empirical refitting requires separately authorized access to the harmonized study dataset. The tables are not interchangeable estimates of a common outcome and must not be read as causal effects.
