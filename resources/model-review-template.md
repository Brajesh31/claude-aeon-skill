# Time-Series Model Review

Record each candidate consistently so that model selection is reproducible and the trade-offs remain visible.

## Experiment Details

- **Experiment ID:**
- **Date:**
- **Owner:**
- **Dataset / version:**
- **Code revision:**
- **Python and Aeon versions:**
- **Random seed(s):**

## Problem and Validation

- **Task:**
- **Target / event definition:**
- **Unit of analysis:**
- **Prediction horizon:**
- **Validation strategy:**
- **Group or time boundaries:**
- **Primary metric:**
- **Secondary metrics:**

## Candidate Configuration

- **Estimator:**
- **Aeon module:**
- **Hyperparameters:**
- **Preprocessing:**
- **Feature extraction:**
- **Training duration:**
- **Inference latency:**
- **Memory / hardware notes:**

## Results

| Metric | Baseline | Candidate | Difference |
|---|---:|---:|---:|
| Primary metric | | | |
| Secondary metric 1 | | | |
| Secondary metric 2 | | | |
| Important subgroup | | | |

- **Variation across folds / periods:**
- **Performance by forecast horizon, if applicable:**
- **Thresholding approach, if applicable:**

## Failure Analysis

- **Common error patterns:**
- **Weak time periods or entities:**
- **Sensitivity to missing data:**
- **Drift or distribution-shift concerns:**
- **Potential leakage or evaluation caveats:**

## Decision

- [ ] Reject
- [ ] Run another experiment
- [ ] Keep as a baseline
- [ ] Recommend for further validation
- [ ] Approve for a controlled deployment

**Reasoning:**

**Conditions before deployment:**

**Monitoring signals:**

**Rollback or fallback plan:**

**Reviewer and date:**

## Reproducibility Checklist

- [ ] Data version and preprocessing are recorded.
- [ ] Split indices or split-generation logic are saved.
- [ ] Estimator parameters and random seeds are recorded.
- [ ] Metrics can be regenerated from saved predictions.
- [ ] Limitations and known failure modes are documented.
