# Aeon Time Series Machine Learning Skill

A Claude Code skill for building, evaluating, and improving time-series machine learning workflows with [Aeon](https://www.aeon-toolkit.org/). It covers classification, regression, clustering, forecasting, anomaly detection, segmentation, similarity search, feature extraction, and temporal distance measures.

## What This Skill Covers

| Problem type | Typical objective | Main reference |
|---|---|---|
| Classification | Assign a label to a complete series | [Classification](references/classification.md) |
| Regression | Predict a continuous target from temporal data | [Regression](references/regression.md) |
| Clustering | Group similar series without labels | [Clustering](references/clustering.md) |
| Forecasting | Predict future observations | [Forecasting](references/forecasting.md) |
| Anomaly detection | Find unusual points, windows, or series | [Anomaly detection](references/anomaly_detection.md) |
| Segmentation | Detect regime changes and boundaries | [Segmentation](references/segmentation.md) |
| Similarity search | Retrieve repeated or similar subsequences | [Similarity search](references/similarity_search.md) |
| Transformations | Normalize and transform time-series collections | [Transformations](references/transformations.md) |
| Distance analysis | Compare sequences with temporal distance functions | [Distances](references/distances.md) |
| Deep learning | Use neural architectures for temporal tasks | [Networks](references/networks.md) |
| Benchmarking | Load benchmark datasets and compare estimators | [Datasets and benchmarking](references/datasets_benchmarking.md) |

## When to Use It

Use this skill when a task involves ordered observations, timestamps, repeated measurements, or sequential patterns and a time-series-specific method is appropriate. It can help select estimators, prepare data, extract features, design validation, compare models, and interpret results.

It is not a substitute for domain knowledge or a defensible evaluation design. Result quality depends on the sampling process, target definition, data quality, split strategy, and metric selection.

## Installation

Install Aeon in the Python environment used for the project:

~~~bash
python -m pip install aeon
~~~

Or, when using uv:

~~~bash
uv pip install aeon
~~~

Clone the skill into the Claude Code skills directory:

~~~bash
git clone https://github.com/Brajesh31/claude-aeon-skill.git ~/.claude/skills/aeon
~~~

Invoke it in Claude Code with:

~~~text
/aeon
~~~

## Workflow

1. **Define the prediction task.** Specify the unit of analysis, target, prediction horizon, and how the result will be used.
2. **Inspect the time axis.** Record sampling frequency, timestamps, missing intervals, series lengths, and whether observations are regular or irregular.
3. **Inspect the collection.** Check the number of series, number of channels, scale differences, entity identifiers, and target distribution.
4. **Choose a defensible split.** Use chronological, rolling-origin, or group-aware validation when time or entity boundaries matter.
5. **Establish a baseline.** Start with a simple method that is difficult to beat accidentally.
6. **Select a suitable Aeon estimator.** Match the algorithm to the task, data volume, series length, compute budget, and interpretability needs.
7. **Fit transformations correctly.** Learn preprocessing parameters from training data only and apply the fitted transformation to validation or test data.
8. **Evaluate the right outcome.** Report task-relevant metrics, uncertainty where possible, and performance against the baseline.
9. **Review failure cases.** Inspect residuals, difficult series, false alerts, unstable segments, and performance across relevant groups.
10. **Record the experiment.** Capture the data version, split, estimator, parameters, random seeds, metrics, limitations, and next action.

## Important Evaluation Guidance

Time-series validation is not interchangeable with a random split. A random split can leak future information into training, or place observations from the same subject, device, or customer in both training and test sets.

Choose the split based on the deployment question:

- **Future prediction:** train on earlier observations and evaluate on later observations.
- **Generalization to unseen entities:** keep entity groups separate across splits.
- **Repeated forecasting:** use rolling-origin or expanding-window evaluation.
- **Independent series classification:** use stratification when appropriate, while checking whether series from the same source must remain together.

Fit scalers, imputers, feature selection, and other learned transformations on the training partition only. Keep a final holdout untouched until model selection is complete.

## Included Resources

- [Problem definition template](resources/problem-definition-template.md): capture the data shape, task, target, horizon, and constraints before choosing a model.
- [Time-series validation checklist](resources/validation-checklist.md): review leakage risks, split strategy, preprocessing, baselines, and evaluation.
- [Model review template](resources/model-review-template.md): document experiments, compare candidates, and record limitations and deployment considerations.

## Existing Reference Guides

The `references/` directory provides topic-focused guides for classification, regression, clustering, forecasting, anomaly detection, segmentation, similarity search, transformations, distances, networks, and benchmarking. Start with [SKILL.md](SKILL.md), then open the relevant reference.

## Repository Structure

~~~text
claude-aeon-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── references/
│   ├── anomaly_detection.md
│   ├── classification.md
│   ├── clustering.md
│   ├── datasets_benchmarking.md
│   ├── distances.md
│   ├── forecasting.md
│   ├── networks.md
│   ├── regression.md
│   ├── segmentation.md
│   ├── similarity_search.md
│   └── transformations.md
└── resources/
    ├── model-review-template.md
    ├── problem-definition-template.md
    └── validation-checklist.md
~~~

## External Documentation

- [Aeon documentation](https://www.aeon-toolkit.org/)
- [Aeon GitHub repository](https://github.com/aeon-toolkit/aeon)
- [Aeon examples](https://www.aeon-toolkit.org/en/stable/examples.html)
- [Aeon API reference](https://www.aeon-toolkit.org/en/stable/api_reference.html)

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root `LICENSE` file for the complete terms.
