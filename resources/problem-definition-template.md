# Time-Series Problem Definition

Use this template before choosing an Aeon estimator. A precise problem definition prevents model selection from driving the problem statement.

## Project Context

- **Project / experiment:**
- **Owner:**
- **Date:**
- **Decision this model will support:**

## Task Definition

- **Task type:** classification / regression / forecasting / clustering / anomaly detection / segmentation / similarity search / other
- **Unit of analysis:** one series / one entity / one window / one timestamp / other
- **Target or event definition:**
- **Prediction horizon or window length:**
- **When is a prediction required?**
- **What action follows the prediction?**

## Data Profile

- **Data source and version:**
- **Number of series:**
- **Number of channels per series:**
- **Typical and maximum series length:**
- **Sampling frequency:**
- **Regular or irregular timestamps:**
- **Time zone and timestamp convention:**
- **Entity or group identifiers:**
- **Missing-value pattern:**
- **Label or target distribution:**
- **Known data-quality issues:**

## Constraints

- **Latency requirement:**
- **Memory / compute budget:**
- **CPU or GPU availability:**
- **Interpretability requirement:**
- **Class imbalance or rare-event concern:**
- **Privacy or data-retention constraints:**

## Validation Plan

- **Deployment scenario:** future observations / new entities / both / other
- **Split strategy:**
- **Grouping key, if applicable:**
- **Baseline method:**
- **Primary metric:**
- **Secondary metrics:**
- **Important slices or subgroups:**
- **Leakage risks to investigate:**

## Initial Decision

- **Candidate Aeon estimator(s):**
- **Why these candidates fit the problem:**
- **Preprocessing to test:**
- **Experiments to run:**
- **Known limitations:**
- **Review date:**

## Completion Check

- [ ] Target and unit of analysis are unambiguous.
- [ ] The forecast horizon or observation window is explicit.
- [ ] Sampling and timestamp assumptions are recorded.
- [ ] Entity boundaries and possible leakage are understood.
- [ ] Validation matches the intended deployment scenario.
- [ ] A simple baseline and primary metric are defined.
