# Explainable AI Benchmarking Engine

**A practical framework for measuring how faithful, stable, efficient,
and interpretable machine-learning explanations are.**

Machine-learning models can make accurate predictions without making
their reasoning easy to inspect. This project explores a more systematic
way to evaluate explainability methods by measuring explanation quality
rather than treating an explanation as automatically trustworthy.

The project was developed as part of an MSc dissertation in
Human-Centred Artificial Intelligence.

## What it does

The Metrics Engine runs a structured evaluation workflow for model
explanations. It is designed to help compare explainability approaches
across models and datasets using quantitative metrics and reproducible
outputs.

-   **Fidelity:** Measures how closely a local explanation approximates
    the behaviour of the original model.
-   **Stability:** Evaluates whether explanations remain similar when
    small changes are made to an input.
-   **Runtime:** Records the time required to generate explanations.
-   **Complexity / sparsity:** Measures how compact an explanation is,
    supporting analysis of its interpretability.
-   **Degree of Explanation (DoX):** Combines selected metric results
    into an overall score for comparison. The score is experimental and
    should be interpreted alongside its component metrics, not as a
    universal measure of explainability.

## Workflow

1.  Load a dataset and prepare the features for modelling.
2.  Train or load a machine-learning model.
3.  Generate local explanations, including surrogate-based explanations.
4.  Calculate fidelity, stability, runtime, and complexity-related
    metrics.
5.  Aggregate the results into structured reports.
6.  Compare results across evaluated models and explanation settings.

## Outputs

The project includes analysis outputs such as:

-   CSV summaries of model and explainability metrics
-   JSON reports containing detailed evaluation results
-   Fidelity distribution visualisations
-   Local surrogate coefficient tables and plots

Example output fields include model name, number of test samples,
predictive accuracy, ROC-AUC, mean and median local fidelity, fidelity
variation, stability, runtime, complexity/sparsity, and DoX.

## Datasets and models

The project materials include experiments and data resources associated
with:

-   Adult Income
-   Bank Marketing
-   UCI Credit Card Default

The available results include a Random Forest classifier evaluation.
Exact models, sample sizes, and metrics may differ between experiments;
consult the corresponding report or output file before comparing runs.

## Repository contents

A typical project layout can be organised as follows. Adjust the names
to match the files you publish:

``` text
.
├── data/                 # Dataset files or instructions for obtaining them
├── src/                  # Metrics engine and evaluation code
├── results/
│   ├── metrics_engine_summary.csv
│   ├── metrics_engine_report.json
│   └── figures/
├── notebooks/            # Experiment notebooks, if included
├── requirements.txt      # Python dependencies
└── README.md
```

Only include directories and files that are actually present in your
GitHub repository.

## Getting started

### 1. Clone the repository

``` bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_DIRECTORY>
```

### 2. Set up the environment

Use a virtual environment to keep dependencies isolated:

``` bash
python -m venv .venv
```

Activate it:

**macOS / Linux**

``` bash
source .venv/bin/activate
```

**Windows**

``` bash
.venv\Scripts\activate
```

Install the project dependencies once the repository's
`requirements.txt` is available:

``` bash
pip install -r requirements.txt
```

### 3. Run the evaluation

The exact command depends on the entry-point script included in the
repository. Add the verified command here after confirming the final
source layout.

## Interpreting the results

No single metric captures every aspect of explainability. A method may
closely approximate a model while producing complex explanations, or
generate explanations quickly while being less stable. Review the
component metrics together and consider the model, dataset, and intended
user context when interpreting the DoX score.

The current work is an experimental benchmarking framework, not a
certification that a model or explanation is safe, fair, or suitable for
a particular decision.

## Research focus

This project investigates how explainability evaluation can become more
measurable, repeatable, and useful in machine-learning workflows. It
connects quantitative evaluation with a human-centred question: are
explanations faithful to model behaviour, stable under small changes,
and practical to inspect?

## Limitations

-   Metric values depend on the model, dataset, explainer configuration,
    and evaluation procedure.
-   Stability scores depend on the perturbations and similarity measure
    used.
-   Simplicity or sparsity does not automatically mean an explanation is
    understandable to a person.
-   A composite score can hide trade-offs between its component metrics.
-   Human-centred usefulness requires user-focused evaluation; it cannot
    be established by numerical metrics alone.

## Citation

If you use or build on this work, please cite the project using the
dissertation details below once the final bibliographic information is
confirmed:

``` text
Gunasekaran, Vibhooshan. Automating Explainability: A Benchmarking Framework
for Interpreting Machine Learning Models. MSc dissertation,
Technological University Dublin.
```

## Author

**Vibhooshan Gunasekaran**\
MSc Human-Centred Artificial Intelligence\
Technological University Dublin
