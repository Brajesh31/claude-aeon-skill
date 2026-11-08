# claude-aeon-skill

A Claude Code skill for time-series machine learning with the Aeon toolkit.

## Overview

Aeon is a Python toolkit for machine learning with temporal and sequential data. It provides specialized estimators and workflows for tasks that are not always handled well by general-purpose tabular machine learning methods.

This skill helps select appropriate time-series methods, prepare temporal datasets, compare algorithms, and evaluate results without ignoring the ordering and structure of observations.

## Supported Problem Types

- **Classification:** Assign labels to complete time series.
- **Regression:** Predict continuous targets from temporal observations.
- **Clustering:** Group series with similar patterns.
- **Forecasting:** Estimate future observations from historical values.
- **Anomaly detection:** Identify unusual series or subsequences.
- **Segmentation:** Detect boundaries or changes within a sequence.
- **Similarity search:** Retrieve series that resemble a query.
- **Transformation:** Convert or normalize time-series representations.
- **Feature extraction:** Generate useful representations for downstream models.

## Installation

```bash
python -m pip install aeon
```

Install the skill:

```bash
git clone https://github.com/Brajesh31/claude-aeon-skill.git ~/.claude/skills/aeon
```

## Usage

Use the skill when a task involves ordered observations, timestamps, repeated measurements, or temporal patterns. Provide the sampling frequency, series length, number of series, target definition, and any missing-data constraints.

Invoke it directly when needed:

```text
/aeon
```

## Typical Workflow

1. Identify whether the problem is classification, regression, forecasting, clustering, or another time-series task.
2. Inspect series length, sampling frequency, missing values, and target leakage risks.
3. Select a suitable dataset representation and estimator.
4. Establish a baseline before tuning complex methods.
5. Split data in a way that respects time and entity boundaries.
6. Evaluate with metrics appropriate to the task.
7. Compare results against a simple baseline.
8. Record preprocessing, model configuration, and evaluation protocol.

## Evaluation Considerations

Random train/test splitting can produce misleading results when temporal order matters. Use chronological or grouped evaluation where appropriate. For forecasting, ensure that future observations do not leak into training features. For classification and regression, consider whether samples from the same subject or device must remain in a single split.

## Repository Structure

```text
claude-aeon-skill/
├── SKILL.md
├── references/
│   ├── anomaly-detection/
│   ├── classification/
│   ├── clustering/
│   ├── datasets-and-benchmarking/
│   ├── distances/
│   ├── forecasting/
│   ├── networks/
│   ├── regression/
│   ├── segmentation/
│   ├── similarity-search/
│   └── transformations/
└── README.md
```

The reference directory contains focused material for individual problem families. Start with `SKILL.md`, then consult the relevant topic guide.

## Model Selection Checklist

- Match the estimator to the actual task.
- Check the expected input shape and data type.
- Use a baseline and a defensible validation split.
- Consider series length and dataset size.
- Check computational cost before large searches.
- Report uncertainty and limitations alongside metrics.

## Repository Contents

- `SKILL.md`: Main skill instructions.
- `references/`: Detailed task-specific guides and method notes.
- `README.md`: Installation and workflow overview.
