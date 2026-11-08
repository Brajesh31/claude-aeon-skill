# Time-Series Validation Checklist

Use this checklist before training and before accepting evaluation results. A high score is not persuasive when the validation design does not match the real prediction setting.

## 1. Time and Entity Boundaries

- [ ] The split reflects the intended deployment scenario.
- [ ] Future observations do not appear in training when predicting the future.
- [ ] Series from the same entity are grouped when entity leakage is possible.
- [ ] Overlapping windows do not cross train/test boundaries unintentionally.
- [ ] The prediction horizon and label construction are documented.
- [ ] Any delayed labels or reporting lags are respected.

## 2. Preprocessing and Feature Engineering

- [ ] Imputation parameters are learned from training data only.
- [ ] Scaling and normalization are fitted on training data only.
- [ ] Feature selection is performed inside the validation process.
- [ ] Rolling statistics use only information available at prediction time.
- [ ] Target-derived or future-derived features are excluded.
- [ ] Resampling, interpolation, and window construction are documented.
- [ ] Train and test transformations use identical fitted parameters.

## 3. Baselines and Comparisons

- [ ] A naive or domain-relevant baseline is included.
- [ ] Candidate methods receive comparable data and validation treatment.
- [ ] Hyperparameter tuning does not use the final holdout.
- [ ] Compute cost and training time are recorded.
- [ ] Random seeds and software versions are recorded where relevant.

## 4. Metrics and Reporting

- [ ] Metrics match the business or scientific objective.
- [ ] Class imbalance is considered where relevant.
- [ ] Forecast metrics are computed at the required horizons.
- [ ] Anomaly detection metrics account for event ranges or alert delays where appropriate.
- [ ] Aggregate results do not hide weak performance on important groups.
- [ ] Uncertainty or variation across folds / time periods is reported.
- [ ] The final result is compared with the baseline.

## 5. Robustness and Failure Analysis

- [ ] Residuals or misclassified series have been inspected.
- [ ] Performance is checked across time periods or important entities.
- [ ] Missing data and sensor interruptions are considered.
- [ ] Drift and changes in operating conditions are considered.
- [ ] Thresholds are selected on validation data, not the final test set.
- [ ] Operational failure modes and fallback behavior are documented.

## Sign-Off

- **Dataset / version:**
- **Validation strategy:**
- **Primary metric:**
- **Baseline result:**
- **Candidate result:**
- **Known limitations:**
- **Reviewer:**
- **Date:**

Do not approve a result solely because it is numerically strong. Approve it only when the data split, information availability, metric, and deployment scenario are aligned.
