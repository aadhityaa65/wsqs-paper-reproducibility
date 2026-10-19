# Water Service Quality Score (WSQS) | Study reproducibility

Computational materials accompanying the household water-service-quality measurement and forecasting study by **Aadhityaa Mohanavelu and Khalid K. Osman**.

**Software and repository implementation:** Aadhityaa Mohanavelu.  
**Research supervision and study coauthorship:** Prof. Khalid K. Osman, Stanford University.  
**Version:** `0.1.0`.

This repository provides the WSQS measurement implementation, scientific feature definitions, model configurations, selected evaluation routines and aggregate results. It is a companion to the research article, not a public release of the original household survey data or a complete end-to-end reproduction of every article figure and table.

The separately developed [WSQS toolkit](https://github.com/aadhityaa65/wsqs-toolkit) provides a more general-purpose implementation.

## Contents

- `src/wsqs/`, `run.py` and `run_extended.py` contain scoring, predictor construction and model evaluation code.
- `config/` and `questionbook/` document the model and questionnaire-variable specifications.
- `results/aggregate/` provides selected empirical evaluation summaries, with no household-level predictions.
- `example/` contains 25 wholly synthetic records for verifying code execution.
- `tests/` and `environment/` provide tests and reproducible environment instructions.

The original forecasting model uses 33 predictors comprising 22 service-support variables, three household-context variables and eight stated-priority ratings. Its CORE-7A outcome sensitivity excludes Acceptability and uses 25 service-support and context (SC) predictors. CORE-7B excludes Customer Service and uses all 33 service-support, context and priority (SCP) predictors. Its historical CatBoost fitting procedure is documented in [`docs/REPRODUCE.md`](docs/REPRODUCE.md).

## Getting started

Use Python 3.11 and the dependencies documented in [`docs/VERIFIED_ENVIRONMENT.md`](docs/VERIFIED_ENVIRONMENT.md):

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r environment/requirements-demo.txt
PYTHONPATH=src python -m unittest discover -s tests -v
python run.py --mode demo
python run_extended.py --mode demo
```

The demonstrations operate on synthetic data. They are not empirical model validations.

Researchers who already have authorized access to the harmonized analytical data can run the empirical routines in a new secure output directory **outside** this repository:

```bash
python run.py --mode reproduce --data /secure/authorized_analytical_master.csv --output /secure/new_benchmark_outputs
python run_extended.py --mode reproduce --data /secure/authorized_analytical_master.csv --output /secure/new_extension_outputs
```

For input requirements, analysis coverage and methodological qualifications, consult [`docs/INPUT_SCHEMA.md`](docs/INPUT_SCHEMA.md), [`docs/REPRODUCE.md`](docs/REPRODUCE.md), [`docs/EXTENDED_ANALYSES.md`](docs/EXTENDED_ANALYSES.md) and [`REPRODUCIBILITY_SCOPE.md`](REPRODUCIBILITY_SCOPE.md).

## Data availability and interpretation

The survey microdata, participant identifiers, household-level model predictions and individual feature records are **not distributed**. The published repository contains synthetic inputs and selected aggregate results. Empirical refitting requires separately authorized access to the harmonized analytical dataset. This package does not regenerate every inferential analysis, manuscript figure or supplementary table. Predictive measures and Shapley allocations should not be interpreted as causal effects.

See [`DATA_PRIVACY.md`](DATA_PRIVACY.md) and [`docs/DATA_AVAILABILITY.md`](docs/DATA_AVAILABILITY.md).

## Citation and acknowledgment

If you use these materials in research, cite the associated paper by **Mohanavelu and Osman (2026)** and identify the repository version. The research was developed by Aadhityaa Mohanavelu under the supervision of Prof. Khalid K. Osman. The paper was coauthored by Mohanavelu and Osman; software authorship and research coauthorship are distinguished in [`RIGHTS_AND_ATTRIBUTION.md`](RIGHTS_AND_ATTRIBUTION.md).

**Paper:** Mohanavelu, A., & Osman, K. K. (2026). *Operational Service Conditions are the primary predictors of Household Water Service Quality Across Heterogeneous Provision Systems*. Research Square [Preprint]. https://doi.org/10.21203/rs.3.rs-10888037/v1

The final journal citation should be used when available. [`CITATION.cff`](CITATION.cff) provides machine-readable citation information.

## Licenses

Original software and functional configurations are available under the **[MIT License](LICENSE)**. Original documentation, synthetic demonstration content, questionnaire metadata and distributable aggregate results are available under **[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE-CONTENT.md)**, to the extent rights are held by the licensor. See [`LICENSING.md`](LICENSING.md) for the file-level distinction. These licenses do **not** grant access to restricted study data or rights in third-party materials.

## Provenance

The historical study-reproducibility archive is preserved separately. Its recorded SHA-256 is `f94a1ed639dfb42706c8fff51b0071ff580a4cd6d42638b4e65177d458bb4ba1`. The current repository provides a maintained portable implementation, with its checksums listed in [`PUBLIC_SHA256SUMS.txt`](PUBLIC_SHA256SUMS.txt). Archived project-status documents are historical records, not current instructions for using the software.
