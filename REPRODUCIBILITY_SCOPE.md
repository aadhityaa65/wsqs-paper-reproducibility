# Empirical reproducibility scope and limitations

**Evidence basis:** the 44-file original WSQS reproducibility candidate, frozen on 18 October 2026; the original `docs/ANALYSIS_COVERAGE.md` and `docs/RELEASE_STATUS.json` remain unchanged.

| Analysis or artifact | Scope supported by this archive |
| --- | --- |
| CORE-8, CORE-7A and CORE-7B scoring and 33-feature construction | Implemented and synthetic-unit-tested |
| Primary CatBoost and six benchmark entries | Portable ten-split benchmark with aggregate reference metrics; requires restricted input for refit |
| Service-support (S), context (C), priorities (P) | Seven nonempty block coalitions and Shapley R² output |
| Cross-domain checks | Eight leave-target-domain-out models with aggregate comparisons |
| Alternate outcomes and inputs | Selected CORE-7A, weighting, income, pressure, age and gender sensitivity encodings |
| CORE-7A original outcome sensitivity | 25 SC predictors, held-out RMSE 11.141250646, 285 selected iterations |
| CORE-7B original outcome sensitivity | Historical protocol verified on October 19, 2026 with 33 SCP predictors, matching held-out RMSE 10.968920357 and 461 selected iterations |
| Prior Stage 9 CORE-7B SC comparator | 25 SC predictors, held-out RMSE 11.051243758; distinct specification, not the original CORE-7B fit |
| Extra Trees and Random Forest | Small numerical differences from historical artifacts documented in original audit |
| Primary-model repeated splits | **Not** the same exercise as the seven-learner benchmark; not portable as a separate full reproduction here |
| Priority-null permutations and uncertainty, grouped explanations, service–priority pairs | Not fully reconstructed in this archive |
| Full manuscript and Supplementary tables and figures | **Not** all regenerated here |
| Empirical refitting | Requires separately authorized harmonized analytical data, **not provided** |

The original `docs/ANALYSIS_COVERAGE.md` predates the October 19, 2026 CORE-7B reconciliation and is preserved as historical provenance. Its CORE-7B warning is superseded by the verified 33-predictor reproduction. The `source_specification_sha256` in `config/scientific_plans.json` identifies the original `STEP18B_corrected_pipeline_scaffold.py` scientific specification; that upstream source is not separately included in this package.

**Interpretation:** This is reproducibility *support* with verified portable components and selected archived aggregate results. It is not a turnkey open-data reproduction of the full paper. See `docs/ANALYSIS_COVERAGE.md` for the detailed frozen statement. Predictive and Shapley decompositions are not causal effects.

The original `docs/RELEASE_STATUS.json` records the status of the **frozen research candidate** as of October 2026, including `publication_authorized: false`. That historical file is kept intact for provenance. Repository public-release authorization, if later granted, is a separate administrative decision and does not change historical scientific-coverage status.
