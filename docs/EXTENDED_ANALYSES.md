# Additional scientific analyses

The package implements the seven nonempty predictor-block
coalitions for service-support (S), household context (C)
and stated priorities (P).

Three-block Shapley R² allocation averages each block's
incremental predictive contribution over all possible
coalition entry orders. It is not causal attribution.

Additional outcome specifications include CORE-7A
(excluding Acceptability), CORE-7B (excluding Customer
Service), population-priority weighting and household-
specific priority weighting. Population weights are
calculated on development observations only.

Feature sensitivity specifications comprise reported
income as a nominal predictor, alternative pressure
coding, respondent age and respondent gender.

Cross-domain models exclude service-support predictors
from the target domain. They retain other service-support
predictors, context and priorities. Each model uses its
observed domain outcomes and the common partition.

For a no-data demonstration:

    python run_extended.py --mode demo

For authorized empirical reproduction:

    python run_extended.py --mode reproduce --data /secure/analytical_master.csv --output /secure/new_results_folder

The command creates aggregate evaluation tables only.
It does not write household predictions, respondent
identifiers or survey microdata.

Archived manuscript tables and figures are not replaced
by the demonstration. Empirical runs require separate
authorized data access and verification against the
revised original results.
