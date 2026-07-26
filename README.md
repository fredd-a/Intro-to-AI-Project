# AI-Based Academic Performance Prediction System

Predict a student's future academic performance from current and historical data to flag at-risk students early for intervention.

## Overview

Many students fall behind academically before instructors or advisors can intervene, because declining grades, reduced engagement, and inconsistent study habits often go unnoticed until after a failed exam or low midterm grade. Manually tracking these patterns across a class or cohort is time-consuming and inconsistent. This project builds a system that predicts future academic performance using data such as grades, attendance, and study habits, so instructors and students can act before performance drops significantly.

See the full proposal: [docs/Group12_ProjectProposal.pdf](docs/Group12_ProjectProposal.pdf)

## Team

| Team Member | Role | Primary Responsibilities |
|---|---|---|
| Rafiatou | Project Manager | Keeps timeline on track, writes/compiles the report, prepares the final presentation or demo, coordinates team meetings |
| Fredda | Evaluation & Testing Lead | Tests model accuracy, checks for overfitting/bias |
| Omuwa | Data Engineer | Finds/collects the dataset, cleans and preprocesses data (handling missing values, formatting grades/attendance), documents data sources |
| Mitchelle | AI Engineer | Builds and trains the AI model (e.g. Random Forest), handles feature selection, and tunes model performance |

## Repository Structure

```
Group 12 Project/
├── data/
│   ├── raw/              Raw datasets with SOURCE.md citation files
│   └── processed/        Cleaned and feature-engineered data
├── notebooks/            Project Jupyter notebooks
├── references/           Third-party prior work (not authored by this team)
├── src/                  Reusable Python modules and scripts
├── reports/
│   └── figures/          Generated plots and visualizations
└── docs/                 Project documentation (including the proposal)
```

| Folder | Purpose |
|---|---|
| `data/raw/` | Original, unmodified datasets |
| `data/processed/` | Cleaned and transformed data ready for modeling |
| `notebooks/` | Exploratory analysis and modeling notebooks |
| `references/` | External reference materials (e.g. third-party Kaggle notebooks) |
| `src/` | Reusable Python code shared across notebooks |
| `reports/figures/` | Saved charts and figures for the report |
| `docs/` | Written project documents |

## Dataset

Three raw datasets are stored under `data/raw/`:

| Subfolder | File | Status |
|---|---|---|
| `student_performance_predictions/` | `student_performance_updated_1000.csv` | **Primary dataset** — used for modeling going forward |
| `student_alcohol_consumption/` | `student-mat.csv` | Reference/comparison only — not used in the final model |
| `student_performance_analysis/` | `Student_performance_data _.csv` | Reference/comparison only — not used in the final model |

Citation details for the primary dataset: [data/raw/student_performance_predictions/SOURCE.md](data/raw/student_performance_predictions/SOURCE.md)

## Prior Work / References

`references/prior_work_student_perf_ipynb/` contains a third-party Kaggle notebook (`college-data-exploratory-data-analysis.ipynb`) kept for reference during exploration. It was **not authored by this team**.

The notebook itself does not record a source URL. The closest recorded citation is from the reference materials originally stored alongside it:

- [Joelknapp — Student Performance Analysis (Kaggle)](https://www.kaggle.com/code/joelknapp/student-performance-analysis/input)

## Milestone Plan

| Week | Milestone / Key Deliverables |
|---|---|
| Week 10 | Collect & clean data. Sketch system design. Set up GitHub repo + README |
| Week 11 | Build baseline model (Random Forest). Commit code regularly. |
| Week 12 | Tune model, start evaluation. Bring a working prototype for the progress demo. |
| Week 13 | Finish evaluation. Run ethics/bias audit. Draft report & slides. |

## AI Technique

The candidate technique is **Random Forest**. It works well with mixed data types (grades, attendance, habits) without extensive cleanup, handles missing or messy data, and surfaces which factors matter most — making results easier to explain to instructors. The main trade-offs are potential overfitting on small datasets and reduced interpretability compared to a single decision tree.

The team may re-evaluate and consider other techniques later in the project lifecycle.
