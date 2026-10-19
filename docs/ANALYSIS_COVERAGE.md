# Analysis coverage and reproducibility status

This repository is a research reproducibility candidate,
not an authorized final publication release.

## Verified portable analyses

- CORE-8 WSQS response scoring and 33-predictor construction
- Primary CatBoost and six additional benchmark entries
- Seven nonempty S/C/P predictor-block models
- Three-block Shapley R² attribution
- Eight leave-target-domain-out prediction models
- CORE-7A and alternative priority-weighted outcomes
- Income, pressure, age and gender sensitivity encodings
- CORE-7B scoring and a supplementary fitted model

The portable primary and block-model results reproduce
their recorded performance. Cross-domain models reproduce
the eight archived held-out evaluations.

The seven-learner benchmark reproduces the substantive
model comparisons. Small numerical differences in
Extra Trees and Random Forest remain documented in the
private scientific audit. They did not change model
rankings or the scientific interpretation.

## Important distinctions

The dedicated historical CORE-7B extension reported a
different RMSE from the new Stage 9 CORE-7B fit. These
should not be described as an exact reproduction until
the corresponding predictor specification is reconciled.

The following analyses have archived research evidence
but are not all independently reconstructed in this
portable candidate:

- Priority-null permutation inference and its uncertainty
- The separate primary-model repeated-split analyses
- Grouped feature attribution and service-priority pairs
- Detailed interpretation and response-profile figures
- The proposed full composite cross-domain comparator
- Some manuscript-specific figure and table generation

The Stage 6 ten-split, seven-learner benchmark must not
be confused with the separate primary-model repeated
splits performed during the manuscript revision.

The original main figures and tables are protected.
This candidate does not replace or regenerate them.

## Scientific interpretation

All model results are predictive and descriptive.
Neither block Shapley nor feature attribution establishes
causal effects.

Predictors exclude exact CORE-8 target questions.
Related questions still share survey context and can
measure conceptually similar service experiences.
