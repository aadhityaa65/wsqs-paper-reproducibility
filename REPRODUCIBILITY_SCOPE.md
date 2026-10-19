# Reproducibility scope

This package shares executable study methods and selected aggregate outputs. It supports independent inspection of the original computational choices and execution of synthetic demonstrations. Re-estimation of the empirical models requires separately authorized access to the study's harmonized analytical data.

| Component | Available reproduction material |
| --- | --- |
| CORE-8 measurement and 33-feature construction | Python implementation, manifest, tests and synthetic demonstrations |
| Core predictor-block comparisons | Seven nonempty S/C/P combinations and three-block Shapley R² allocation |
| CORE-7A domain exclusion | Excludes Acceptability; 25 SC predictors; original held-out RMSE 11.141250646 and 285 CatBoost iterations |
| CORE-7B domain exclusion | Excludes Customer Service; 33 SCP predictors; original held-out RMSE 10.968920357 and 461 CatBoost iterations, reproduced under the historical fitting specification |
| Priority-weighted WSQS outcomes | Population- and individual-priority sensitivity implementations using 25 SC predictors |
| Benchmark algorithms | Seven-learner comparison across ten specified data partitions and aggregate benchmark files |
| Cross-domain models | Eight predictor-exclusion specifications and aggregate comparisons |
| Feature sensitivities | Selected income, pressure, age and gender variants |
| Supplementary inference and figure creation | Some procedures and manuscript outputs are outside the portable repository |
| Original empirical data | Not distributed; requires separate authorization |

The ten-partition multi-learner benchmark is distinct from the separate primary-model repeated-split analysis described in the manuscript. The repository does not reproduce every inferential exercise, feature-attribution analysis or supplementary figure. Results based on different outcome definitions should be interpreted as robustness checks, not direct comparisons of identical prediction targets. Block contributions and Shapley allocations are descriptive of prediction, not causal effects.

Historical project files in `docs/ANALYSIS_COVERAGE.md` and `docs/RELEASE_STATUS.json` are preserved for archival provenance. They refer to earlier candidate stages and are not the current statement of scientific scope. The stable computational specifications are described here and in [`docs/REPRODUCE.md`](docs/REPRODUCE.md).
