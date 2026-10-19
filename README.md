# Water Service Quality Score (WSQS) | Original-Study Computational Reproducibility

**Companion code and aggregate evidence for the original household water-service-quality forecasting study.**  
**Repository version:** `v0.1.0` (portable, *partial* empirical reproduction package).  
**Study authors:** Aadhityaa Mohanavelu and Khalid K. Osman.

**Related general-purpose toolkit:** [wsqs-toolkit](https://github.com/aadhityaa65/wsqs-toolkit), separately released as `v0.9.0`.

## Scope at a glance

This repository preserves the original study's CORE-8 scoring and feature-construction code, its model settings, portable benchmark and extension routines, selected aggregate empirical evaluation tables and **25 entirely synthetic examples**. It contains **no observed household-level survey records**, respondent identifiers, individual predictions or private analysis datasets. Its purpose is to expose the computational methods and *documented subset* of reproducible numerical checks, **not** to claim that every manuscript table or figure can be recreated from public inputs.

The original household-level data are restricted. Without separately authorized access to the harmonized analytical dataset, researchers can run the synthetic examples and examine the aggregate evaluation tables, but cannot independently refit the empirical models. See [`docs/DATA_AVAILABILITY.md`](docs/DATA_AVAILABILITY.md), [`docs/ANALYSIS_COVERAGE.md`](docs/ANALYSIS_COVERAGE.md) and [`REPRODUCIBILITY_SCOPE.md`](REPRODUCIBILITY_SCOPE.md).

## Scientific material included

- CORE-8 household WSQS, plus CORE-7A and CORE-7B sensitivity outcome implementations.
- 33 original predictors comprising 22 service-support, three household-context and eight stated-priority variables.
- Primary CatBoost and six benchmark entries, with ten specified repeated seeds for the seven-learner benchmark.
- Seven nonempty S/C/P predictor-block combinations, three-block Shapley decomposition and eight target-domain exclusions.
- Selected outcome and demographic/provider encoding sensitivities.
- Original aggregate benchmark, block, Shapley and cross-domain result files, with methodological qualifications.

Original configurations remain in [`config/`](config/), feature documentation in [`questionbook/`](questionbook/) and aggregate results in [`results/aggregate/`](results/aggregate/).

## Important scientific boundaries

The package **does not fully reproduce the paper**. The historical CORE-7B fitting discrepancy is unresolved. Small Extra Trees and Random Forest numerical differences are documented. Several manuscript analyses, including priority-null permutation inference, the separately executed primary-model repeated-split exercise, feature-attribution pairs and certain figures/tables, are not reconstructed here. The seven-learner repeated-split benchmark is **not** the separate primary-model repeated-split exercise. Predictive and Shapley quantities must not be interpreted causally.

The original archive documented these limits prior to GitHub preparation. Its status metadata in `docs/RELEASE_STATUS.json` is a **historical frozen candidate record**, not an assertion that every manuscript result was reproduced. We have preserved it unchanged. See [`REPRODUCIBILITY_SCOPE.md`](REPRODUCIBILITY_SCOPE.md) for a short coverage matrix.

## Install and run

Use Python 3.11 and the environment described in [`docs/VERIFIED_ENVIRONMENT.md`](docs/VERIFIED_ENVIRONMENT.md):

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r environment/requirements-demo.txt
PYTHONPATH=src python -m unittest discover -s tests -v
python run.py --mode demo
python run_extended.py --mode demo
```

The demonstrations use only 25 synthetic records and **do not refit or verify the empirical results**.

Authorized researchers possessing the separately harmonized original analytical dataset may invoke:

```bash
python run.py --mode reproduce --data /secure/authorized_analytical_master.csv --output /secure/new_benchmark_outputs
python run_extended.py --mode reproduce --data /secure/authorized_analytical_master.csv --output /secure/new_extension_outputs
```

Run each command with a **different, new output directory** outside this repository, as required by the command-line safeguards. Consult [`docs/REPRODUCE.md`](docs/REPRODUCE.md), [`docs/INPUT_SCHEMA.md`](docs/INPUT_SCHEMA.md) and [`docs/EXTENDED_ANALYSES.md`](docs/EXTENDED_ANALYSES.md) first. The raw field-survey instrument and upstream harmonization are not supplied as a turnkey public reproduction pipeline.

## Original archive integrity

The frozen original-study ZIP is maintained separately as a release asset; SHA-256:

`f94a1ed639dfb42706c8fff51b0071ff580a4cd6d42638b4e65177d458bb4ba1`

For the exact historical README and checksum list, see [`docs/FROZEN_ORIGINAL_README.md`](docs/FROZEN_ORIGINAL_README.md) and [`docs/FROZEN_ORIGINAL_SHA256SUMS.txt`](docs/FROZEN_ORIGINAL_SHA256SUMS.txt). All 41 original files *other than* the README, `.gitignore` and working manifest remain byte-for-byte identical to the frozen archive. This GitHub wrapper adds publication metadata and privacy safeguards without changing original scientific code or aggregate research results.

## Privacy, licenses and citation

Read [`DATA_PRIVACY.md`](DATA_PRIVACY.md) before working with restricted data. Keep household-level data and run outputs outside this Git repository. The original Python code is offered under MIT and eligible original documentation and aggregate materials under CC BY 4.0, **subject to confirmation of the applicable rights for this separate archive before making the repository public**. See [`LICENSING.md`](LICENSING.md).

**Research reference:** Mohanavelu, A., & Osman, K. K. (2026). *Operational Service Conditions are the primary predictors of Household Water Service Quality Across Heterogeneous Provision Systems*. Research Square [Preprint]. https://doi.org/10.21203/rs.3.rs-10888037/v1

The journal article citation and DOI should replace the preferred preprint citation when published. The Research Square DOI identifies the **paper**, not this software. GitHub uses the top-level [`CITATION.cff`](CITATION.cff) to display the citation.
