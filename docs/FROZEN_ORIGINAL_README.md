# Water Service Quality Score (WSQS)

Computational materials for household water-service-quality
measurement and forecasting.

## Measurement and predictors

The package implements the eight-domain CORE-8 WSQS, the
CORE-7A and CORE-7B sensitivity outcomes and the original
questionnaire response coding.

The forecasting predictors comprise 22 service-support
variables, three household-context variables and eight
stated-priority variables.

The original response categories, ordinal levels,
provider-dependent applicability handling and feature
specification are provided in `questionbook/` and `config/`.

## Demonstration

The package includes 25 fully synthetic examples. They are
not drawn from the empirical survey.

After installing the dependencies:

    python run.py --mode demo

The demonstration verifies software execution. It must not
be used to estimate or report the study's predictive results.

## Empirical benchmark

With separately authorized access to the harmonized
analytical dataset:

    python run.py --mode reproduce --data /path/to/authorized_analytical_master.csv --output /path/to/secure/new_results_directory

The empirical benchmark fits CatBoost, histogram gradient
boosting, extremely randomized trees, random forest,
ElasticNet and Ridge, alongside a development-sample mean
baseline.

Ten repeated random splits are evaluated. Every model uses
the same test observations within each split. CatBoost tree
counts and Ridge regularization are selected using internal
validation. The remaining comparison models have fixed
hyperparameters.

Outputs comprise aggregate split-level metrics, learner
summaries and run metadata. Household-level predictions are
not exported by the command-line interface.

## Tests

    PYTHONPATH=src python -m unittest discover -s tests -v

## Data availability

Household-level survey data are not distributed in this
repository. Empirical reproduction requires separately
authorized access. See `docs/DATA_ACCESS.md`.

The complete questionnaire harmonization and additional
manuscript analyses are documented separately and will be
included in the final research release after verification.


## Reproducibility status

This is a reviewed research candidate, not the authorized final release. See `docs/ANALYSIS_COVERAGE.md`, `docs/DATA_AVAILABILITY.md` and `docs/RELEASE_STATUS.json` for details. The 25 synthetic examples do not reproduce the original empirical results.
