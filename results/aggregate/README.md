# Verified aggregate results

These CSV files contain aggregate model evaluation
results only. They do not contain survey microdata,
respondent identifiers or individual predictions.

The benchmark files originate from the Stage 6
portable reproduction.

The extended analysis files primarily originate from Stage 9. The CORE7B row in `sensitivity_models.csv` now reflects the original 33-predictor SCP extension, reproduced using its historical fitting protocol on October 19, 2026. The earlier Stage 9 CORE-7B fit used 25 SC predictors (RMSE 11.051243758), which was a separate comparison.

The block comparison and cross-domain comparison
files are checks against archived scientific results.

Small numerical variation should be judged against
the scientific specification, model comparisons and
substantive conclusions, rather than bit-for-bit
floating-point identity.
