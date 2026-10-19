# Computational reproduction

The input for empirical reproduction is the harmonized
household analytical dataset.

The feature schema includes 22 service-support responses,
three context fields, eight priority ratings and a
municipal-supply applicability indicator.

Eight harmonized domain-severity columns construct the
CORE-8 outcome as an average of available applicable
domains, transformed onto a 0–100 scale.

The analysis uses 6,145 household records, with ten
unstratified random splits defined by seeds 20260714
through 20260723.

Each split has 3,932 fitting records, 984 internal
validation records and 1,229 held-out test records.

CatBoost uses 1,400 maximum iterations, a learning rate
of 0.035, depth 5 and validation-based early stopping.
The best iteration count is used to refit the development
sample before held-out evaluation.

Ridge selects alpha from 0.1, 1, 10 and 100 using
validation RMSE. The other learners follow their specified
fixed configurations.

All numerical preprocessing is fitted within the
appropriate training partition. Categorical variables
are handled as categorical features by CatBoost and
through one-hot encoding by scikit-learn estimators.

The benchmark reports RMSE, MAE, R² and Spearman
correlation for each split. Aggregate results are
summarized across ten splits.

No respondent-level data are provided in the public
repository or exported by the reproduction command.
